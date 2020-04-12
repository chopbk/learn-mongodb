**Which of the following is true about pipelines and the Aggregation Framework?**
- The Aggregation Framework provides us many stages to filter and transform our data
- Stages cannot be configured to produce our desired output.
- Documents flow through the pipeline, passing from one stage to the next
- Pipelines must consist of at least two stages.

**Answers**
- The Aggregation Framework provides us many stages to filter and transform our data
        
- Documents flow through the pipeline, passing from one stage to the next

**Let's review this quiz options:**

- Stages cannot be configured to produce our desired output.
    
    `This is definitely not correct`. Các `Stage` có thể cấu hình để tạo đầu ra mong muốn

- Pipelines must consist of at least two stages.
    
    `This is not correct`. Pipeline phải có ít nhất 1 `stage` và có thể có nhiều `stage`

- Documents flow through the pipeline, passing one stage to the next
    
    `This is correct.` `Document` được xử lý theo đường ống, đưa đầu ra của `stage` này thành đầu vào của `stage` phía sau

- The Aggregation Framework provides us many stages to filter and transform our data.
    
    `This is also correct.`