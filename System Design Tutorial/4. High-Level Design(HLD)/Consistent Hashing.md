# Consistent Hashing

## What is Hashing?

Hashing involves using a hash function to produce a pseudo-random number. This number is then divided by the size of the available memory space, resulting in the transformation of the random identifier into a position within the given memory space. This process can be conceptually represented as follows:

![Hashing](https://media.geeksforgeeks.org/wp-content/uploads/20230710174101/Hashing-22.jpg)

In distributed systems, traditional hashing methods often use the following approach to determine which server handles a particular request:

```
serverIndex = hash(key) % N
```

Where N is the number of servers.

## What is Consistent Hashing?

Consistent hashing is a distributed hashing technique used in computer science and distributed systems to achieve load balancing and minimize the need for rehashing when the number of nodes in a system changes. It is particularly useful in distributed hash tables (DHTs), distributed caching systems, and other distributed storage systems.

A method for evenly allocating keys (like cache keys) among a group of nodes (like cache servers) in computer systems is called consistent hashing. Reducing the amount of keys that must be relocated when nodes are added or withdrawn from the cluster aims to reduce the effect that these modifications have on the system as a whole.

![Consistent Hashing](https://media.geeksforgeeks.org/wp-content/uploads/20230421120916/consistent-hashingjpg-22.jpg)

Key features of consistent hashing:
- It represents requests and server nodes in a virtual ring structure known as a **hashring**.
- The number of locations in this ring is not fixed but is considered to have an infinite number of points.
- Server nodes are placed at random locations on this ring using hashing.
- The requests (users, computers, or serverless programs) are also placed on the same ring using the same hash function.

## Issues with Traditional Hashing Methods

Here are some key issues with traditional hashing methods:

### 1. Uneven Distribution of Data

Traditional hashing methods often lead to an uneven distribution of data across servers. When you use a simple hash function, some servers may get more data, while others get very little.

### 2. Scalability Problems

A sizable amount of the data must be redistributed among all servers in classic hashing whenever a server (node) is added or removed. As a result, practically all data must be rehashed and reassigned, which is ineffective and results in delays or downtime.

### 3. Inflexibility with Changing Number of Servers

If your application requires scaling up by adding more servers or scaling down by removing some, traditional hashing methods struggle to adapt. The entire system becomes unstable, and large amounts of data need to be moved.

### 4. Node Failure Handling

When a server fails in a traditional hashing setup, all the data on that server becomes inaccessible until the server is back up or the data is redistributed. There is no good way to handle node failures.

### 5. Overhead of Rehashing

When the system grows or shrinks, traditional hashing requires rehashing of most keys to different servers, which causes a high amount of overhead.

## How to Decide Which Request Will Be Served by Which Server?

If we assume the ring is ordered so that the clockwise traversal of the ring corresponds to the increasing order of location addresses, each request can be served by the server node that first appears while traversing clockwise.

![Mapping in Hashing](https://media.geeksforgeeks.org/wp-content/uploads/20230421120747/Mapping-in-the-hashing-(1).jpg)

## What is the use of Consistent Hashing?

Consistent hashing is a popular technique used in distributed systems to address the challenge of efficiently distributing keys or data elements across multiple nodes/servers in a network. Consistent hashing's primary objective is to reduce the number of remapping operations necessary when adding or removing nodes from the network, which contributes to the stability and dependability of the system.

Key uses include:
- Consistent hashing can be used to share the burden among nodes and lessen the effects of node failures.
- When a new node is added to the network, only a small number of keys are remapped to the new node, which helps to reduce the overhead associated with the addition.
- Similarly, when a node fails, only a small number of keys are affected, which helps to minimize the impact of the failure on the system as a whole.
- Consistent hashing is also useful in ensuring data availability and consistency in a distributed system.

## Phases/Working of Consistent Hashing

The following are the phases involved in the process of consistent hashing:

### Phase 1: Hash Function Selection

Selecting the hash algorithm to link keys to network nodes is the first stage in consistent hashing. This hash function should be deterministic and produce a different value for each key. The selected hash function will be used to map keys to nodes in a consistent and predictable manner.

### Phase 2: Node Assignment

In this phase, each node in the network is assigned a position on the hash ring using the selected hash function. This assignment creates a virtual ring structure with nodes placed at different positions around the ring.

### Phase 3: Key Mapping

Once the nodes are placed on the hash ring, the keys are mapped to the nodes by hashing them using the same hash function and placing them on the ring. Each key is assigned to the node that is closest to it in the clockwise direction on the hash ring.

### Phase 4: Node Addition

When a new node is added to the network, it is placed at a specific position on the hash ring using the hash function. Only the keys that fall between the new node and its predecessor on the ring are remapped to the new node. All other keys remain unchanged, thus minimizing the amount of redistribution required.

### Phase 5: Load Redistribution

Consistent hashing helps in distributing the load among the network's nodes. To keep the system balanced and effective when a node is overloaded, portions of its keys can be remapped to other nodes.

### Phase 6: Failure Recovery

If a node fails, the keys that are assigned to it can be remapped to other nodes in the network. This enables data to remain accurate and always available, even in the case of a node failure.

For example:
Let's say we have 5 nodes in the ring and say node 3 fails, then the range of the next server node widens and any request coming in all of this range, goes to the new server node. This shows that due to use of consistent hashing only a small portion of keys are affected.

![Node Failure Example](https://media.geeksforgeeks.org/wp-content/uploads/20230421121059/Node-Failure-Example.jpg)

## Implementation of Consistent Hashing Algorithm

### Step 1: Choose a Hash Function

Select a hash function that produces a uniformly distributed range of hash values. Common choices include MD5, SHA-1, or SHA-256.

### Step 2: Create a Virtual Ring

Create a virtual ring or circle representing the hash value space. This is often represented as a range from 0 to 2^32 - 1.

### Step 3: Place Servers on the Ring

For each server, compute its hash value using the chosen hash function and place it on the ring at the corresponding position.

### Step 4: Place Virtual Nodes (Optional)

To improve load balancing, create multiple virtual nodes for each physical server. Each virtual node gets its own position on the ring.

### Step 5: Map Keys to Servers

For each key, compute its hash value and find the next server node in the clockwise direction on the ring. This server is responsible for handling the key.

### Step 6: Handle Server Addition/Removal

When a server is added or removed, only the keys that fall between the affected server and its predecessor (counterclockwise) need to be remapped.

```cpp
#include <bits/stdc++.h>
using namespace std;

class ConsistentHashRing {
private:
    map<int, string> ring;
    set<int> sorted_keys;
    int replicas;

    int get_hash(const string& key) {
        // Simple hash function for demonstration purposes
        int hash = 0;
        for (char c : key) {
            hash = (hash * 31 + c) % INT_MAX;
        }
        return hash;
    }

public:
    ConsistentHashRing(int num_replicas = 3) : replicas(num_replicas) {}

    void add_node(const string& node) {
        for (int i = 0; i < replicas; ++i) {
            string virtual_node = node + "#" + to_string(i);
            int hash = get_hash(virtual_node);
            ring[hash] = node;
            sorted_keys.insert(hash);
        }
    }

    void remove_node(const string& node) {
        for (int i = 0; i < replicas; ++i) {
            string virtual_node = node + "#" + to_string(i);
            int hash = get_hash(virtual_node);
            ring.erase(hash);
            sorted_keys.erase(hash);
        }
    }

    string get_node(const string& key) {
        if (ring.empty()) {
            return "";
        }

        int hash = get_hash(key);
        
        // Find the first node whose hash is greater than or equal to the key's hash
        auto it = sorted_keys.lower_bound(hash);
        
        // If no such node exists, wrap around to the first node
        if (it == sorted_keys.end()) {
            it = sorted_keys.begin();
        }
        
        return ring[*it];
    }
};

int main() {
    ConsistentHashRing ring;
    
    // Add server nodes
    ring.add_node("Node_A");
    ring.add_node("Node_B");
    ring.add_node("Node_C");
    
    // Map keys to nodes
    cout << "The key 'first_key' is mapped to node: " << ring.get_node("first_key") << endl;
    cout << "The key 'second_key' is mapped to node: " << ring.get_node("second_key") << endl;
    cout << "The key 'third_key' is mapped to node: " << ring.get_node("third_key") << endl;
    
    // Remove a node and see how keys are remapped
    cout << "\nRemoving Node_B...\n" << endl;
    ring.remove_node("Node_B");
    
    cout << "After removal, the key 'first_key' is mapped to node: " << ring.get_node("first_key") << endl;
    cout << "After removal, the key 'second_key' is mapped to node: " << ring.get_node("second_key") << endl;
    cout << "After removal, the key 'third_key' is mapped to node: " << ring.get_node("third_key") << endl;
    
    return 0;
}
```

Note: This example uses a simple hash function and a binary search to find the position on the ring.

## Advantages of using Consistent Hashing

Below are some of the key advantages of using consistent hashing:

### 1. Load Balancing

Even as the volume of data grows and evolves over time, consistent hashing maintains the system's efficiency and responsiveness by distributing the network's workload among its nodes in a balanced way.

### 2. Scalability

Because consistent hashing is so scalable, it can adjust to variations in the number of nodes or volume of data being processed with negligible to no impact on the system's overall performance.

### 3. Minimal Remapping

By minimizing the amount of keys that need to be remapped whenever a node is added or withdrawn, consistent hashing makes sure that the system remains stable and reliable even as the network evolves.

### 4. Increased Failure Tolerance

Consistent hashing makes data always accessible and current, even in the case of node failures. The stability and dependability of the system as a whole are enhanced by the capacity to replicate keys across several nodes and remap them to different nodes in the event of failure.

### 5. Simplified Operations

The act of adding or removing nodes from the network is made easier by consistent hashing, which makes it simpler to administer and maintain a sizable distributed system.

## Disadvantages of using Consistent Hashing

### 1. Hash Function Complexity

The effectiveness of consistent hashing depends on the use of a suitable hash function. The hash function must produce a unique value for each key and be deterministic in order to be useful. The system's overall effectiveness and efficiency may be affected by how complicated the hash function is.

### 2. Performance Cost

The computing resources needed to map keys to nodes, replicate keys, and remap keys in the event of node additions or removals can result in some performance overhead when using consistent hashing.

### 3. Lack of Flexibility

In some circumstances, the system's ability to adapt to changing requirements or shifting network conditions may be constrained by the rigid limits of consistent hashing.

### 4. High Resource Use

As nodes are added to or deleted from the network, consistent hashing may occasionally result in high resource utilization. This can have an effect on the system's overall performance and efficacy.

### 5. Complexity of Management

Managing and maintaining a system that uses consistent hashing can be difficult and demanding, and it often calls for particular expertise and abilities.

## Real-world Applications of Consistent Hashing

Consistent hashing is used in many distributed systems and applications, including:

1. **Content Delivery Networks (CDNs)**: CDNs use consistent hashing to distribute content across edge servers, ensuring that user requests are directed to the closest server with the requested content.

2. **Distributed Databases**: Databases like Apache Cassandra use consistent hashing to distribute data across multiple nodes in a cluster, making it easier to scale horizontally.

3. **Distributed Caching Systems**: Memcached and Redis use consistent hashing to distribute cache keys across multiple cache servers.

4. **Load Balancers**: Some load balancers use consistent hashing to distribute incoming requests across backend servers, ensuring that requests for the same resource are always directed to the same server.

5. **Peer-to-Peer Networks**: DHTs (Distributed Hash Tables) in P2P networks like BitTorrent use consistent hashing to locate resources in the network.

## Conclusion

Consistent hashing is a powerful technique for distributing data across multiple nodes in a distributed system. It provides a solution to the problem of remapping a large number of keys when the number of nodes changes, making it an essential tool for building scalable, resilient distributed systems.

By minimizing the amount of data that needs to be redistributed when the topology of the system changes, consistent hashing helps maintain system stability and performance. While it has some limitations and complexities, the benefits it provides in terms of load balancing, scalability, and fault tolerance make it a valuable tool in the arsenal of distributed system designers.

---

# Băm nhất quán (Consistent Hashing)

## Băm là gì?

Băm liên quan đến việc sử dụng một hàm băm để tạo ra một số giả ngẫu nhiên. Số này sau đó được chia cho kích thước của không gian bộ nhớ khả dụng, dẫn đến sự chuyển đổi của số định danh ngẫu nhiên thành một vị trí trong không gian bộ nhớ đã cho. Quá trình này có thể được thể hiện một cách khái niệm như sau:

![Hashing](https://media.geeksforgeeks.org/wp-content/uploads/20230710174101/Hashing-22.jpg)

Trong các hệ thống phân tán, các phương pháp băm truyền thống thường sử dụng cách tiếp cận sau để xác định máy chủ nào xử lý một yêu cầu cụ thể:

```
chỉSốMáyChủ = băm(khóa) % N
```

Trong đó N là số lượng máy chủ.

## Băm nhất quán là gì?

Băm nhất quán là một kỹ thuật băm phân tán được sử dụng trong khoa học máy tính và các hệ thống phân tán để đạt được cân bằng tải và giảm thiểu nhu cầu băm lại khi số lượng nút trong hệ thống thay đổi. Nó đặc biệt hữu ích trong các bảng băm phân tán (DHTs), hệ thống bộ nhớ đệm phân tán và các hệ thống lưu trữ phân tán khác.

Một phương pháp phân bổ đồng đều các khóa (như khóa bộ nhớ đệm) giữa một nhóm các nút (như máy chủ bộ nhớ đệm) trong hệ thống máy tính được gọi là băm nhất quán. Giảm số lượng khóa phải được di chuyển khi các nút được thêm vào hoặc rút khỏi cụm nhằm mục đích giảm tác động mà những thay đổi này có trên toàn bộ hệ thống.

![Consistent Hashing](https://media.geeksforgeeks.org/wp-content/uploads/20230421120916/consistent-hashingjpg-22.jpg)

Các tính năng chính của băm nhất quán:
- Nó đại diện cho các yêu cầu và nút máy chủ trong một cấu trúc vòng ảo được gọi là **hashring**.
- Số lượng vị trí trong vòng này không cố định mà được coi là có vô số điểm.
- Các nút máy chủ được đặt ở các vị trí ngẫu nhiên trên vòng này bằng cách sử dụng băm.
- Các yêu cầu (người dùng, máy tính hoặc chương trình serverless) cũng được đặt trên cùng một vòng bằng cách sử dụng cùng một hàm băm.

## Các vấn đề với phương pháp băm truyền thống

Dưới đây là một số vấn đề chính với các phương pháp băm truyền thống:

### 1. Phân phối dữ liệu không đồng đều

Các phương pháp băm truyền thống thường dẫn đến phân phối dữ liệu không đồng đều trên các máy chủ. Khi bạn sử dụng một hàm băm đơn giản, một số máy chủ có thể nhận được nhiều dữ liệu, trong khi những máy chủ khác nhận được rất ít.

### 2. Vấn đề về khả năng mở rộng

Một lượng đáng kể dữ liệu phải được phân phối lại giữa tất cả các máy chủ trong băm cổ điển bất cứ khi nào một máy chủ (nút) được thêm vào hoặc loại bỏ. Kết quả là, thực tế tất cả dữ liệu phải được băm lại và gán lại, điều này không hiệu quả và dẫn đến sự chậm trễ hoặc thời gian ngừng hoạt động.

### 3. Thiếu tính linh hoạt khi thay đổi số lượng máy chủ

Nếu ứng dụng của bạn yêu cầu mở rộng quy mô bằng cách thêm nhiều máy chủ hoặc thu hẹp quy mô bằng cách loại bỏ một số, các phương pháp băm truyền thống gặp khó khăn trong việc thích ứng. Toàn bộ hệ thống trở nên không ổn định và một lượng lớn dữ liệu cần được di chuyển.

### 4. Xử lý lỗi nút

Khi một máy chủ gặp sự cố trong thiết lập băm truyền thống, tất cả dữ liệu trên máy chủ đó trở nên không thể truy cập cho đến khi máy chủ hoạt động trở lại hoặc dữ liệu được phân phối lại. Không có cách tốt nào để xử lý lỗi nút.

### 5. Chi phí băm lại

Khi hệ thống phát triển hoặc co lại, băm truyền thống yêu cầu băm lại hầu hết các khóa đến các máy chủ khác nhau, điều này gây ra một lượng lớn chi phí.

## Làm thế nào để quyết định yêu cầu nào sẽ được phục vụ bởi máy chủ nào?

Nếu chúng ta giả định rằng vòng được sắp xếp sao cho việc duyệt vòng theo chiều kim đồng hồ tương ứng với thứ tự tăng dần của địa chỉ vị trí, mỗi yêu cầu có thể được phục vụ bởi nút máy chủ xuất hiện đầu tiên khi duyệt theo chiều kim đồng hồ.

![Mapping in Hashing](https://media.geeksforgeeks.org/wp-content/uploads/20230421120747/Mapping-in-the-hashing-(1).jpg)

## Mục đích sử dụng của Băm nhất quán là gì?

Băm nhất quán là một kỹ thuật phổ biến được sử dụng trong hệ thống phân tán để giải quyết thách thức phân phối hiệu quả các khóa hoặc các phần tử dữ liệu trên nhiều nút/máy chủ trong một mạng. Mục tiêu chính của Băm nhất quán là giảm số lượng hoạt động ánh xạ lại cần thiết khi thêm hoặc xóa nút khỏi mạng, điều này góp phần vào sự ổn định và đáng tin cậy của hệ thống.

Các mục đích sử dụng chính bao gồm:
- Băm nhất quán có thể được sử dụng để chia sẻ gánh nặng giữa các nút và giảm bớt tác động của lỗi nút.
- Khi một nút mới được thêm vào mạng, chỉ một số lượng nhỏ khóa được ánh xạ lại đến nút mới, điều này giúp giảm chi phí liên quan đến việc thêm nút.
- Tương tự, khi một nút gặp sự cố, chỉ một số lượng nhỏ khóa bị ảnh hưởng, điều này giúp giảm thiểu tác động của sự cố đến toàn bộ hệ thống.
- Băm nhất quán cũng hữu ích trong việc đảm bảo tính khả dụng và nhất quán của dữ liệu trong hệ thống phân tán.

## Các giai đoạn/Cách thức hoạt động của Băm nhất quán

Sau đây là các giai đoạn liên quan đến quá trình băm nhất quán:

### Giai đoạn 1: Lựa chọn hàm băm

Việc chọn thuật toán băm để liên kết các khóa với các nút mạng là giai đoạn đầu tiên trong băm nhất quán. Hàm băm này phải là xác định và tạo ra một giá trị khác nhau cho mỗi khóa. Hàm băm được chọn sẽ được sử dụng để ánh xạ các khóa đến các nút một cách nhất quán và có thể dự đoán.

### Giai đoạn 2: Gán nút

Trong giai đoạn này, mỗi nút trong mạng được gán một vị trí trên vòng băm bằng cách sử dụng hàm băm đã chọn. Việc gán này tạo ra một cấu trúc vòng ảo với các nút được đặt ở các vị trí khác nhau xung quanh vòng.

### Giai đoạn 3: Ánh xạ khóa

Sau khi các nút được đặt trên vòng băm, các khóa được ánh xạ đến các nút bằng cách băm chúng bằng cùng một hàm băm và đặt chúng trên vòng. Mỗi khóa được gán cho nút gần nhất với nó theo hướng kim đồng hồ trên vòng băm.

### Giai đoạn 4: Thêm nút

Khi một nút mới được thêm vào mạng, nó được đặt ở một vị trí cụ thể trên vòng băm bằng cách sử dụng hàm băm. Chỉ các khóa nằm giữa nút mới và nút tiền nhiệm của nó trên vòng được ánh xạ lại đến nút mới. Tất cả các khóa khác vẫn không thay đổi, do đó giảm thiểu lượng phân phối lại cần thiết.

### Giai đoạn 5: Phân phối lại tải

Băm nhất quán giúp phân phối tải giữa các nút của mạng. Để giữ cho hệ thống cân bằng và hiệu quả khi một nút bị quá tải, các phần của các khóa của nó có thể được ánh xạ lại đến các nút khác.

### Giai đoạn 6: Khôi phục lỗi

Nếu một nút gặp sự cố, các khóa được gán cho nó có thể được ánh xạ lại đến các nút khác trong mạng. Điều này cho phép dữ liệu vẫn chính xác và luôn khả dụng, ngay cả trong trường hợp nút gặp sự cố.

Ví dụ:
Giả sử chúng ta có 5 nút trong vòng và giả sử nút 3 gặp sự cố, thì phạm vi của nút máy chủ tiếp theo sẽ mở rộng và bất kỳ yêu cầu nào đến trong tất cả phạm vi này đều chuyển đến nút máy chủ mới. Điều này cho thấy do sử dụng băm nhất quán, chỉ một phần nhỏ khóa bị ảnh hưởng.

![Node Failure Example](https://media.geeksforgeeks.org/wp-content/uploads/20230421121059/Node-Failure-Example.jpg)

## Triển khai thuật toán Băm nhất quán

### Bước 1: Chọn một hàm băm

Chọn một hàm băm tạo ra một dải giá trị băm phân phối đồng đều. Các lựa chọn phổ biến bao gồm MD5, SHA-1 hoặc SHA-256.

### Bước 2: Tạo một vòng ảo

Tạo một vòng ảo hoặc vòng tròn đại diện cho không gian giá trị băm. Điều này thường được biểu diễn như một phạm vi từ 0 đến 2^32 - 1.

### Bước 3: Đặt máy chủ trên vòng

Đối với mỗi máy chủ, tính toán giá trị băm của nó bằng cách sử dụng hàm băm đã chọn và đặt nó trên vòng ở vị trí tương ứng.

### Bước 4: Đặt nút ảo (Tùy chọn)

Để cải thiện cân bằng tải, tạo nhiều nút ảo cho mỗi máy chủ vật lý. Mỗi nút ảo có vị trí riêng của nó trên vòng.

### Bước 5: Ánh xạ khóa đến máy chủ

Đối với mỗi khóa, tính toán giá trị băm của nó và tìm nút máy chủ tiếp theo theo hướng kim đồng hồ trên vòng. Máy chủ này chịu trách nhiệm xử lý khóa.

### Bước 6: Xử lý việc thêm/xóa máy chủ

Khi một máy chủ được thêm vào hoặc xóa đi, chỉ các khóa nằm giữa máy chủ bị ảnh hưởng và tiền nhiệm của nó (ngược chiều kim đồng hồ) cần được ánh xạ lại.

```cpp
#include <bits/stdc++.h>
using namespace std;

class ConsistentHashRing {
private:
    map<int, string> ring;
    set<int> sorted_keys;
    int replicas;

    int get_hash(const string& key) {
        // Hàm băm đơn giản cho mục đích minh họa
        int hash = 0;
        for (char c : key) {
            hash = (hash * 31 + c) % INT_MAX;
        }
        return hash;
    }

public:
    ConsistentHashRing(int num_replicas = 3) : replicas(num_replicas) {}

    void add_node(const string& node) {
        for (int i = 0; i < replicas; ++i) {
            string virtual_node = node + "#" + to_string(i);
            int hash = get_hash(virtual_node);
            ring[hash] = node;
            sorted_keys.insert(hash);
        }
    }

    void remove_node(const string& node) {
        for (int i = 0; i < replicas; ++i) {
            string virtual_node = node + "#" + to_string(i);
            int hash = get_hash(virtual_node);
            ring.erase(hash);
            sorted_keys.erase(hash);
        }
    }

    string get_node(const string& key) {
        if (ring.empty()) {
            return "";
        }

        int hash = get_hash(key);
        
        // Tìm nút đầu tiên có giá trị băm lớn hơn hoặc bằng giá trị băm của khóa
        auto it = sorted_keys.lower_bound(hash);
        
        // Nếu không có nút nào như vậy, quay vòng đến nút đầu tiên
        if (it == sorted_keys.end()) {
            it = sorted_keys.begin();
        }
        
        return ring[*it];
    }
};

int main() {
    ConsistentHashRing ring;
    
    // Thêm các nút máy chủ
    ring.add_node("Node_A");
    ring.add_node("Node_B");
    ring.add_node("Node_C");
    
    // Ánh xạ các khóa đến các nút
    cout << "Khóa 'first_key' được ánh xạ đến nút: " << ring.get_node("first_key") << endl;
    cout << "Khóa 'second_key' được ánh xạ đến nút: " << ring.get_node("second_key") << endl;
    cout << "Khóa 'third_key' được ánh xạ đến nút: " << ring.get_node("third_key") << endl;
    
    // Xóa một nút và xem cách các khóa được ánh xạ lại
    cout << "\nĐang xóa Node_B...\n" << endl;
    ring.remove_node("Node_B");
    
    cout << "Sau khi xóa, khóa 'first_key' được ánh xạ đến nút: " << ring.get_node("first_key") << endl;
    cout << "Sau khi xóa, khóa 'second_key' được ánh xạ đến nút: " << ring.get_node("second_key") << endl;
    cout << "Sau khi xóa, khóa 'third_key' được ánh xạ đến nút: " << ring.get_node("third_key") << endl;
    
    return 0;
}
```

Lưu ý: Ví dụ này sử dụng một hàm băm đơn giản và tìm kiếm nhị phân để tìm vị trí trên vòng.

## Ưu điểm của việc sử dụng Băm nhất quán

Dưới đây là một số ưu điểm chính của việc sử dụng băm nhất quán:

### 1. Cân bằng tải

Ngay cả khi khối lượng dữ liệu tăng lên và phát triển theo thời gian, băm nhất quán duy trì hiệu quả và khả năng phản hồi của hệ thống bằng cách phân phối khối lượng công việc của mạng giữa các nút một cách cân bằng.

### 2. Khả năng mở rộng

Vì băm nhất quán có khả năng mở rộng cao, nó có thể điều chỉnh theo sự thay đổi về số lượng nút hoặc khối lượng dữ liệu đang được xử lý với tác động không đáng kể hoặc không có tác động đến hiệu suất tổng thể của hệ thống.

### 3. Giảm thiểu việc ánh xạ lại

Bằng cách giảm thiểu số lượng khóa cần được ánh xạ lại bất cứ khi nào một nút được thêm vào hoặc rút lui, băm nhất quán đảm bảo rằng hệ thống vẫn ổn định và đáng tin cậy ngay cả khi mạng phát triển.

### 4. Tăng khả năng chịu lỗi

Băm nhất quán giúp dữ liệu luôn có thể truy cập và cập nhật, ngay cả trong trường hợp nút gặp sự cố. Sự ổn định và độ tin cậy của toàn bộ hệ thống được tăng cường bởi khả năng sao chép khóa trên nhiều nút và ánh xạ lại chúng đến các nút khác nhau trong trường hợp xảy ra lỗi.

### 5. Đơn giản hóa các hoạt động

Việc thêm hoặc xóa các nút khỏi mạng được dễ dàng hơn bởi băm nhất quán, điều này giúp đơn giản hóa việc quản lý và duy trì một hệ thống phân tán lớn.

## Nhược điểm của việc sử dụng Băm nhất quán

### 1. Độ phức tạp của hàm băm

Hiệu quả của băm nhất quán phụ thuộc vào việc sử dụng một hàm băm phù hợp. Hàm băm phải tạo ra một giá trị duy nhất cho mỗi khóa và phải xác định để có thể hữu ích. Hiệu quả và hiệu suất tổng thể của hệ thống có thể bị ảnh hưởng bởi độ phức tạp của hàm băm.

### 2. Chi phí hiệu suất

Các tài nguyên tính toán cần thiết để ánh xạ khóa đến các nút, sao chép khóa và ánh xạ lại khóa trong trường hợp thêm hoặc xóa nút có thể dẫn đến một số chi phí hiệu suất khi sử dụng băm nhất quán.

### 3. Thiếu tính linh hoạt

Trong một số trường hợp, khả năng của hệ thống để thích ứng với các yêu cầu thay đổi hoặc điều kiện mạng thay đổi có thể bị hạn chế bởi các giới hạn cứng nhắc của băm nhất quán.

### 4. Sử dụng tài nguyên cao

Khi các nút được thêm vào hoặc xóa khỏi mạng, băm nhất quán đôi khi có thể dẫn đến việc sử dụng tài nguyên cao. Điều này có thể có tác động đến hiệu suất và hiệu quả tổng thể của hệ thống.

### 5. Độ phức tạp của quản lý

Quản lý và duy trì một hệ thống sử dụng băm nhất quán có thể khó khăn và đòi hỏi nhiều, và nó thường đòi hỏi kiến thức chuyên môn và kỹ năng cụ thể.

## Ứng dụng thực tế của Băm nhất quán

Băm nhất quán được sử dụng trong nhiều hệ thống và ứng dụng phân tán, bao gồm:

1. **Mạng phân phối nội dung (CDNs)**: CDN sử dụng băm nhất quán để phân phối nội dung trên các máy chủ biên, đảm bảo rằng các yêu cầu của người dùng được chuyển hướng đến máy chủ gần nhất có nội dung được yêu cầu.

2. **Cơ sở dữ liệu phân tán**: Các cơ sở dữ liệu như Apache Cassandra sử dụng băm nhất quán để phân phối dữ liệu trên nhiều nút trong một cụm, giúp dễ dàng mở rộng theo chiều ngang.

3. **Hệ thống bộ nhớ đệm phân tán**: Memcached và Redis sử dụng băm nhất quán để phân phối khóa bộ nhớ đệm trên nhiều máy chủ bộ nhớ đệm.

4. **Bộ cân bằng tải**: Một số bộ cân bằng tải sử dụng băm nhất quán để phân phối các yêu cầu đến trên nhiều máy chủ backend, đảm bảo rằng các yêu cầu cho cùng một tài nguyên luôn được chuyển hướng đến cùng một máy chủ.

5. **Mạng ngang hàng**: DHT (Bảng băm phân tán) trong mạng P2P như BitTorrent sử dụng băm nhất quán để định vị tài nguyên trong mạng.

## Kết luận

Băm nhất quán là một kỹ thuật mạnh mẽ để phân phối dữ liệu trên nhiều nút trong một hệ thống phân tán. Nó cung cấp một giải pháp cho vấn đề ánh xạ lại một số lượng lớn khóa khi số lượng nút thay đổi, làm cho nó trở thành một công cụ thiết yếu để xây dựng hệ thống phân tán có thể mở rộng, linh hoạt.

Bằng cách giảm thiểu lượng dữ liệu cần được phân phối lại khi cấu trúc liên kết của hệ thống thay đổi, băm nhất quán giúp duy trì sự ổn định và hiệu suất của hệ thống. Mặc dù nó có một số hạn chế và phức tạp, những lợi ích mà nó cung cấp về mặt cân bằng tải, khả năng mở rộng và khả năng chịu lỗi làm cho nó trở thành một công cụ có giá trị trong kho vũ khí của các nhà thiết kế hệ thống phân tán.