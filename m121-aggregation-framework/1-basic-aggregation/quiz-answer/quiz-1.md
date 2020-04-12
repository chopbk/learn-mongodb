## $match: Filtering documents
**Which of the following is/are true of the $match stage?**
- It uses the familiar MongoDB query language.
- $match can only filter documents on one field.
- $match can use both query operators and aggregation expressions.
- It should come very early in an aggregation pipeline.

**Answers**
- **It uses the familiar MongoDB query language.**
        
- **It should come very early in an aggregation pipeline.**

**Let's review this quiz options:**

-  $match can only filter documents on one field.
    
    `This is definitely not correct`. `$match` được sử dụng tương tự các truy vấn tìm kiếm của Mongodb => truy vấn trên nhiều trường.

- It uses the familiar MongoDB query language.
    
    `This is correct.` 

- It should come very early in an aggregation pipeline.
    
    `This is also correct.` `$match` giúp cho các stage sau giảm được khối lượng tính toán