## Aggregation Structure and Syntax
**Which of the following statements is true??**
- Only one expression per stage can be used.
- Some expressions can only be used in certain stages.
- An aggregation pipeline is an array of stages.

**Answers**
- Some expressions can only be used in certain stages.
        
- An aggregation pipeline is an array of stages.

**Let's review this quiz options:**

-  Only one expression per stage can be used.
    
    `This is definitely not correct`. Các `Stage` có thể bao gồm nhiều `expression` 

- Some expressions can only be used in certain stages.
    
    `This is correct.` Một số `expressions` chỉ sử dụng được ở stage nhất định, ví dụ các `accumulator expressions` (`addToSet, $sumn, $max`) chỉ sử dụng được với `$group` stage

- An aggregation pipeline is an array of stages.
    
    `This is also correct.`