# Normalization Process in DBMS

## English Version

Database normalization is a systematic process of organizing database schema to minimize data redundancy and dependency. It involves dividing large tables into smaller, more manageable pieces to eliminate duplicate data and ensure data integrity. The normalization procedure relies on identifying and establishing functional dependencies among attributes within tables and follows several standard forms to guide the design process.

## What is Normalization in DBMS?

Normalization is a technique for producing a set of relations with desirable properties that support the requirements of a user or an enterprise. The primary goals of normalization are:

- Eliminating redundant data
- Ensuring data dependencies make sense (only storing related data in a table)
- Reducing the potential for anomalies during data operations (insert, update, delete)
- Improving data integrity

The concept was introduced by E.F. Codd, the inventor of the relational database model, in the 1970s. Before Codd's normalization framework, data was commonly stored in large, unstructured files, which led to significant redundancy and consistency problems.

## Why is Normalization Important?

Normalization addresses several critical problems in database design:

1. **Reducing Data Redundancy**: By eliminating duplicate data, normalized databases require less storage space and reduce the risk of inconsistencies.

2. **Preventing Anomalies**: Properly normalized databases help prevent:
   - **Update Anomalies**: The need to change data in multiple places
   - **Insertion Anomalies**: The inability to add data without the presence of other data
   - **Deletion Anomalies**: Unintentional loss of data when deleting related information

3. **Improving Query Performance**: While complex queries might require joins, normalized databases often perform better for insert, update, and delete operations.

4. **Enhancing Data Integrity**: By organizing data logically, normalization helps ensure accuracy and consistency across the database.

5. **Facilitating Database Maintenance**: Normalized databases are easier to maintain and modify as business requirements evolve.

## Types of Normal Forms

The normalization process involves several levels or "normal forms," each addressing specific types of data redundancy and dependency issues. 

### First Normal Form (1NF)

A relation is in First Normal Form if:
- All attributes contain only atomic (indivisible) values
- Each column contains values from the same domain
- Each attribute has a unique name
- The order in which data is stored doesn't matter

#### Example of 1NF:

**Before 1NF:**
```
Student_Courses Table:
| Student_ID | Name        | Courses            |
|------------|-------------|--------------------|
| 1          | Naveen Kumar | DBMS, OS           |
| 2          | Utkarsh     | CN, COA            |
```

**After 1NF:**
```
Student_Courses Table:
| Student_ID | Name        | Course |
|------------|-------------|--------|
| 1          | Naveen Kumar | DBMS   |
| 1          | Naveen Kumar | OS     |
| 2          | Utkarsh     | CN     |
| 2          | Utkarsh     | COA    |
```

In this example, we've eliminated the multi-valued attribute "Courses" by creating separate rows for each course.

### Second Normal Form (2NF)

A relation is in Second Normal Form if:
- It is in 1NF
- All non-key attributes are fully functionally dependent on the primary key (not on just part of the key)

2NF addresses partial dependency, which occurs when an attribute depends on only part of a composite primary key.

#### Example of 2NF:

**Before 2NF:**
```
Student_Courses Table:
| Student_ID | Course_ID | Student_Name | Course_Name |
|------------|-----------|--------------|-------------|
| 1          | C1        | Naveen       | DBMS        |
| 1          | C2        | Naveen       | OS          |
| 2          | C1        | Utkarsh      | DBMS        |
```

Here, the primary key is the combination of Student_ID and Course_ID, but Student_Name depends only on Student_ID (partial dependency).

**After 2NF:**
```
Student Table:
| Student_ID | Student_Name |
|------------|--------------|
| 1          | Naveen       |
| 2          | Utkarsh      |

Courses Table:
| Course_ID | Course_Name |
|-----------|-------------|
| C1        | DBMS        |
| C2        | OS          |

Student_Courses Table:
| Student_ID | Course_ID |
|------------|-----------|
| 1          | C1        |
| 1          | C2        |
| 2          | C1        |
```

Now all non-key attributes are fully dependent on their respective primary keys.

### Third Normal Form (3NF)

A relation is in Third Normal Form if:
- It is in 2NF
- No non-key attribute is transitively dependent on the primary key (i.e., no non-key attribute depends on another non-key attribute)

3NF addresses transitive dependencies, which occur when a non-key attribute depends on another non-key attribute.

#### Example of 3NF:

**Before 3NF:**
```
Student Table:
| Student_ID | Student_Name | Department_ID | Department_Name |
|------------|--------------|---------------|----------------|
| 1          | Naveen       | D1            | Computer Science|
| 2          | Utkarsh      | D2            | Electrical Eng. |
```

Here, Department_Name depends on Department_ID, which depends on Student_ID (transitive dependency).

**After 3NF:**
```
Student Table:
| Student_ID | Student_Name | Department_ID |
|------------|--------------|---------------|
| 1          | Naveen       | D1            |
| 2          | Utkarsh      | D2            |

Department Table:
| Department_ID | Department_Name |
|---------------|----------------|
| D1            | Computer Science|
| D2            | Electrical Eng. |
```

Now transitive dependencies have been eliminated.

### Boyce-Codd Normal Form (BCNF)

A relation is in Boyce-Codd Normal Form if:
- It is in 3NF
- For every functional dependency X → Y, X is a superkey

BCNF is a stronger form of 3NF that handles some cases of redundancy not addressed by 3NF.

#### Example of BCNF:

**Before BCNF:**
```
Course_Instructors Table:
| Student_ID | Course_ID | Instructor |
|------------|-----------|------------|
| 1          | C1        | Professor A|
| 2          | C1        | Professor A|
| 3          | C2        | Professor B|
```

If each course has only one instructor (Course_ID → Instructor) and students can take multiple courses, this table is in 3NF but not in BCNF because Course_ID is not a superkey.

**After BCNF:**
```
Courses Table:
| Course_ID | Instructor |
|-----------|------------|
| C1        | Professor A|
| C2        | Professor B|

Student_Courses Table:
| Student_ID | Course_ID |
|------------|-----------|
| 1          | C1        |
| 2          | C1        |
| 3          | C2        |
```

Now all functional dependencies are based on superkeys.

### Fourth Normal Form (4NF)

A relation is in Fourth Normal Form if:
- It is in BCNF
- It has no multi-valued dependencies

4NF deals with multi-valued dependencies that can cause redundancy.

### Fifth Normal Form (5NF)

A relation is in Fifth Normal Form if:
- It is in 4NF
- It cannot be decomposed further without loss of information

5NF addresses join dependencies that aren't implied by candidate keys.

## Denormalization: The Counter-Process

While normalization helps improve data integrity and reduce redundancy, sometimes a completely normalized database might lead to complex queries requiring multiple joins, which can impact performance. In such cases, **denormalization** might be applied.

Denormalization is the process of deliberately introducing redundancy by combining tables to optimize read performance at the expense of some write performance. It is typically done after normalization when performance requirements demand it.

## Normalization Strategy and Best Practices

1. **Start with 3NF or BCNF**: For most applications, achieving Third Normal Form or Boyce-Codd Normal Form is usually sufficient.

2. **Consider Use Cases**: Always keep in mind how the data will be accessed and used when designing your schema.

3. **Balance Normalization with Performance**: Be ready to strategically denormalize if query performance becomes an issue.

4. **Document Dependencies**: Clearly document the functional dependencies in your design to make future modifications easier.

5. **Use Normalization as a Guide**: Remember that normalization provides guidelines, not strict rules. The optimal design depends on specific application requirements.

## Summary of Normalization in a Nutshell

| Normal Form | Test | Remedy (Normalization) |
|-------------|------|------------------------|
| 1NF | Check for non-atomic values | Decompose attributes until only atomic values exist |
| 2NF | Check for partial dependencies | Create separate tables for sets of attributes that depend on part of the primary key |
| 3NF | Check for transitive dependencies | Create separate tables for sets of attributes that depend on non-key attributes |
| BCNF | Check for functional dependencies where the determinant is not a superkey | Create separate tables for functional dependencies |
| 4NF | Check for multi-valued dependencies | Split tables to remove multi-valued dependencies |
| 5NF | Check for join dependencies | Decompose into smaller tables that can be rejoined without loss of information |

## Conclusion

The process of normalization in databases ensures that an efficient, organized, and consistent database is created by avoiding redundancy and anomalies during data operations. Databases can be modeled into normal forms starting from 1NF to BCNF and beyond to maintain data integrity and improve database performance.

Each normal form addresses specific redundancies and dependencies, resulting in a well-organized schema for accurate data management and retrieval. While complete normalization is theoretically ideal, practical database design often involves finding the right balance between normalization (for data integrity) and denormalization (for performance).

---

# Quy Trình Chuẩn Hóa trong DBMS

## Phiên Bản Tiếng Việt

Chuẩn hóa cơ sở dữ liệu là một quá trình có hệ thống nhằm tổ chức lược đồ cơ sở dữ liệu để giảm thiểu sự dư thừa và phụ thuộc dữ liệu. Nó liên quan đến việc chia các bảng lớn thành các phần nhỏ hơn, dễ quản lý hơn để loại bỏ dữ liệu trùng lặp và đảm bảo tính toàn vẹn dữ liệu. Quy trình chuẩn hóa dựa trên việc xác định và thiết lập các phụ thuộc hàm giữa các thuộc tính trong bảng và tuân theo một số dạng chuẩn để hướng dẫn quá trình thiết kế.

## Chuẩn Hóa trong DBMS là gì?

Chuẩn hóa là một kỹ thuật để tạo ra một tập hợp các quan hệ với các thuộc tính mong muốn hỗ trợ các yêu cầu của người dùng hoặc doanh nghiệp. Các mục tiêu chính của chuẩn hóa là:

- Loại bỏ dữ liệu dư thừa
- Đảm bảo các phụ thuộc dữ liệu hợp lý (chỉ lưu trữ dữ liệu liên quan trong một bảng)
- Giảm khả năng xảy ra bất thường trong các thao tác dữ liệu (thêm, cập nhật, xóa)
- Cải thiện tính toàn vẹn dữ liệu

Khái niệm này được giới thiệu bởi E.F. Codd, người sáng chế ra mô hình cơ sở dữ liệu quan hệ, vào những năm 1970. Trước khi có khung chuẩn hóa của Codd, dữ liệu thường được lưu trữ trong các tệp lớn, không có cấu trúc, dẫn đến sự dư thừa và các vấn đề nhất quán đáng kể.

## Tại sao Chuẩn Hóa Quan Trọng?

Chuẩn hóa giải quyết một số vấn đề quan trọng trong thiết kế cơ sở dữ liệu:

1. **Giảm Dư Thừa Dữ Liệu**: Bằng cách loại bỏ dữ liệu trùng lặp, cơ sở dữ liệu đã chuẩn hóa yêu cầu ít không gian lưu trữ hơn và giảm nguy cơ không nhất quán.

2. **Ngăn Chặn Bất Thường**: Cơ sở dữ liệu được chuẩn hóa đúng cách giúp ngăn chặn:
   - **Bất Thường Cập Nhật**: Nhu cầu thay đổi dữ liệu ở nhiều nơi
   - **Bất Thường Chèn**: Không thể thêm dữ liệu khi không có dữ liệu khác
   - **Bất Thường Xóa**: Mất dữ liệu không mong muốn khi xóa thông tin liên quan

3. **Cải Thiện Hiệu Suất Truy Vấn**: Mặc dù các truy vấn phức tạp có thể yêu cầu các phép join, cơ sở dữ liệu đã chuẩn hóa thường hoạt động tốt hơn cho các thao tác chèn, cập nhật và xóa.

4. **Tăng Cường Tính Toàn Vẹn Dữ Liệu**: Bằng cách tổ chức dữ liệu một cách hợp lý, chuẩn hóa giúp đảm bảo tính chính xác và nhất quán trên toàn cơ sở dữ liệu.

5. **Tạo Điều Kiện Thuận Lợi Cho Bảo Trì Cơ Sở Dữ Liệu**: Cơ sở dữ liệu đã chuẩn hóa dễ dàng bảo trì và sửa đổi khi yêu cầu kinh doanh phát triển.

## Các Dạng Chuẩn Hóa

Quá trình chuẩn hóa bao gồm nhiều cấp độ hoặc "dạng chuẩn", mỗi dạng giải quyết các vấn đề cụ thể về dư thừa dữ liệu và phụ thuộc.

### Dạng Chuẩn 1 (1NF)

Một quan hệ ở Dạng Chuẩn 1 nếu:
- Tất cả các thuộc tính chứa giá trị nguyên tử (không thể chia nhỏ)
- Mỗi cột chứa giá trị từ cùng một miền giá trị
- Mỗi thuộc tính có một tên duy nhất
- Thứ tự lưu trữ dữ liệu không quan trọng

#### Ví dụ về 1NF:

**Trước 1NF:**
```
Bảng Sinh_Viên_Khóa_Học:
| Mã_SV | Tên        | Khóa_Học           |
|-------|------------|--------------------|
| 1     | Naveen Kumar | DBMS, OS           |
| 2     | Utkarsh     | CN, COA            |
```

**Sau 1NF:**
```
Bảng Sinh_Viên_Khóa_Học:
| Mã_SV | Tên        | Khóa_Học |
|-------|------------|----------|
| 1     | Naveen Kumar | DBMS     |
| 1     | Naveen Kumar | OS       |
| 2     | Utkarsh     | CN       |
| 2     | Utkarsh     | COA      |
```

Trong ví dụ này, chúng ta đã loại bỏ thuộc tính đa trị "Khóa_Học" bằng cách tạo các hàng riêng biệt cho mỗi khóa học.

### Dạng Chuẩn 2 (2NF)

Một quan hệ ở Dạng Chuẩn 2 nếu:
- Nó ở dạng 1NF
- Tất cả các thuộc tính không khóa đều phụ thuộc toàn bộ vào khóa chính (không chỉ vào một phần của khóa)

2NF giải quyết sự phụ thuộc một phần, xảy ra khi một thuộc tính phụ thuộc vào chỉ một phần của khóa chính hỗn hợp.

#### Ví dụ về 2NF:

**Trước 2NF:**
```
Bảng Sinh_Viên_Khóa_Học:
| Mã_SV | Mã_Khóa_Học | Tên_SV   | Tên_Khóa_Học |
|-------|-------------|----------|--------------|
| 1     | C1          | Naveen   | DBMS         |
| 1     | C2          | Naveen   | OS           |
| 2     | C1          | Utkarsh  | DBMS         |
```

Ở đây, khóa chính là sự kết hợp của Mã_SV và Mã_Khóa_Học, nhưng Tên_SV chỉ phụ thuộc vào Mã_SV (phụ thuộc một phần).

**Sau 2NF:**
```
Bảng Sinh_Viên:
| Mã_SV | Tên_SV   |
|-------|----------|
| 1     | Naveen   |
| 2     | Utkarsh  |

Bảng Khóa_Học:
| Mã_Khóa_Học | Tên_Khóa_Học |
|-------------|--------------|
| C1          | DBMS         |
| C2          | OS           |

Bảng Sinh_Viên_Khóa_Học:
| Mã_SV | Mã_Khóa_Học |
|-------|-------------|
| 1     | C1          |
| 1     | C2          |
| 2     | C1          |
```

Bây giờ tất cả các thuộc tính không khóa đều phụ thuộc đầy đủ vào khóa chính tương ứng của chúng.

### Dạng Chuẩn 3 (3NF)

Một quan hệ ở Dạng Chuẩn 3 nếu:
- Nó ở dạng 2NF
- Không có thuộc tính không khóa nào phụ thuộc bắc cầu vào khóa chính (tức là, không có thuộc tính không khóa nào phụ thuộc vào một thuộc tính không khóa khác)

3NF giải quyết các phụ thuộc bắc cầu, xảy ra khi một thuộc tính không khóa phụ thuộc vào một thuộc tính không khóa khác.

#### Ví dụ về 3NF:

**Trước 3NF:**
```
Bảng Sinh_Viên:
| Mã_SV | Tên_SV   | Mã_Khoa  | Tên_Khoa       |
|-------|----------|----------|----------------|
| 1     | Naveen   | D1       | Khoa học máy tính|
| 2     | Utkarsh  | D2       | Kỹ thuật điện  |
```

Ở đây, Tên_Khoa phụ thuộc vào Mã_Khoa, mà phụ thuộc vào Mã_SV (phụ thuộc bắc cầu).

**Sau 3NF:**
```
Bảng Sinh_Viên:
| Mã_SV | Tên_SV   | Mã_Khoa  |
|-------|----------|----------|
| 1     | Naveen   | D1       |
| 2     | Utkarsh  | D2       |

Bảng Khoa:
| Mã_Khoa  | Tên_Khoa       |
|----------|----------------|
| D1       | Khoa học máy tính|
| D2       | Kỹ thuật điện  |
```

Bây giờ các phụ thuộc bắc cầu đã được loại bỏ.

### Dạng Chuẩn Boyce-Codd (BCNF)

Một quan hệ ở Dạng Chuẩn Boyce-Codd nếu:
- Nó ở dạng 3NF
- Đối với mọi phụ thuộc hàm X → Y, X là một siêu khóa

BCNF là một dạng mạnh hơn của 3NF xử lý một số trường hợp dư thừa không được giải quyết bởi 3NF.

#### Ví dụ về BCNF:

**Trước BCNF:**
```
Bảng Giảng_Viên_Khóa_Học:
| Mã_SV | Mã_Khóa_Học | Giảng_Viên |
|-------|-------------|------------|
| 1     | C1          | Giáo sư A  |
| 2     | C1          | Giáo sư A  |
| 3     | C2          | Giáo sư B  |
```

Nếu mỗi khóa học chỉ có một giảng viên (Mã_Khóa_Học → Giảng_Viên) và sinh viên có thể học nhiều khóa học, bảng này ở dạng 3NF nhưng không ở BCNF vì Mã_Khóa_Học không phải là siêu khóa.

**Sau BCNF:**
```
Bảng Khóa_Học:
| Mã_Khóa_Học | Giảng_Viên |
|-------------|------------|
| C1          | Giáo sư A  |
| C2          | Giáo sư B  |

Bảng Sinh_Viên_Khóa_Học:
| Mã_SV | Mã_Khóa_Học |
|-------|-------------|
| 1     | C1          |
| 2     | C1          |
| 3     | C2          |
```

Bây giờ tất cả các phụ thuộc hàm đều dựa trên siêu khóa.

### Dạng Chuẩn 4 (4NF)

Một quan hệ ở Dạng Chuẩn 4 nếu:
- Nó ở dạng BCNF
- Nó không có phụ thuộc đa trị

4NF xử lý các phụ thuộc đa trị có thể gây ra dư thừa.

### Dạng Chuẩn 5 (5NF)

Một quan hệ ở Dạng Chuẩn 5 nếu:
- Nó ở dạng 4NF
- Nó không thể bị phân tách thêm mà không mất thông tin

5NF xử lý các phụ thuộc kết nối không bị ngụ ý bởi các khóa ứng viên.

## Phi Chuẩn Hóa: Quá Trình Ngược Lại

Mặc dù chuẩn hóa giúp cải thiện tính toàn vẹn dữ liệu và giảm dư thừa, đôi khi một cơ sở dữ liệu được chuẩn hóa hoàn toàn có thể dẫn đến các truy vấn phức tạp đòi hỏi nhiều phép join, điều này có thể ảnh hưởng đến hiệu suất. Trong những trường hợp như vậy, **phi chuẩn hóa** có thể được áp dụng.

Phi chuẩn hóa là quá trình cố ý đưa vào sự dư thừa bằng cách kết hợp các bảng để tối ưu hóa hiệu suất đọc với cái giá của một số hiệu suất ghi. Nó thường được thực hiện sau khi chuẩn hóa khi các yêu cầu hiệu suất đòi hỏi.

## Chiến Lược Chuẩn Hóa và Các Thực Hành Tốt Nhất

1. **Bắt Đầu với 3NF hoặc BCNF**: Đối với hầu hết các ứng dụng, việc đạt được Dạng Chuẩn 3 hoặc Dạng Chuẩn Boyce-Codd thường là đủ.

2. **Xem Xét Trường Hợp Sử Dụng**: Luôn ghi nhớ cách dữ liệu sẽ được truy cập và sử dụng khi thiết kế lược đồ của bạn.

3. **Cân Bằng Chuẩn Hóa với Hiệu Suất**: Sẵn sàng phi chuẩn hóa một cách chiến lược nếu hiệu suất truy vấn trở thành vấn đề.

4. **Tài Liệu Hóa Các Phụ Thuộc**: Tài liệu hóa rõ ràng các phụ thuộc hàm trong thiết kế của bạn để việc sửa đổi trong tương lai dễ dàng hơn.

5. **Sử Dụng Chuẩn Hóa như Một Hướng Dẫn**: Hãy nhớ rằng chuẩn hóa cung cấp hướng dẫn, không phải quy tắc nghiêm ngặt. Thiết kế tối ưu phụ thuộc vào các yêu cầu ứng dụng cụ thể.

## Tóm Tắt Quá Trình Chuẩn Hóa

| Dạng Chuẩn | Kiểm Tra | Giải Pháp (Chuẩn Hóa) |
|------------|----------|------------------------|
| 1NF | Kiểm tra các giá trị không nguyên tử | Phân tách các thuộc tính cho đến khi chỉ còn các giá trị nguyên tử |
| 2NF | Kiểm tra phụ thuộc một phần | Tạo bảng riêng biệt cho các tập thuộc tính phụ thuộc vào một phần của khóa chính |
| 3NF | Kiểm tra phụ thuộc bắc cầu | Tạo bảng riêng biệt cho các tập thuộc tính phụ thuộc vào các thuộc tính không khóa |
| BCNF | Kiểm tra phụ thuộc hàm khi yếu tố quyết định không phải là siêu khóa | Tạo bảng riêng biệt cho các phụ thuộc hàm |
| 4NF | Kiểm tra phụ thuộc đa trị | Tách bảng để loại bỏ phụ thuộc đa trị |
| 5NF | Kiểm tra phụ thuộc kết nối | Phân tách thành các bảng nhỏ hơn có thể được kết nối lại mà không mất thông tin |

## Kết Luận

Quá trình chuẩn hóa trong cơ sở dữ liệu đảm bảo rằng một cơ sở dữ liệu hiệu quả, có tổ chức và nhất quán được tạo ra bằng cách tránh sự dư thừa và các bất thường trong quá trình thao tác dữ liệu. Cơ sở dữ liệu có thể được mô hình hóa thành các dạng chuẩn bắt đầu từ 1NF đến BCNF và hơn thế nữa để duy trì tính toàn vẹn dữ liệu và cải thiện hiệu suất cơ sở dữ liệu.

Mỗi dạng chuẩn giải quyết các dư thừa và phụ thuộc cụ thể, dẫn đến một lược đồ có tổ chức tốt để quản lý và truy xuất dữ liệu chính xác. Mặc dù chuẩn hóa hoàn toàn là lý tưởng về mặt lý thuyết, thiết kế cơ sở dữ liệu thực tế thường liên quan đến việc tìm ra sự cân bằng phù hợp giữa chuẩn hóa (để đảm bảo tính toàn vẹn dữ liệu) và phi chuẩn hóa (để đạt hiệu suất).