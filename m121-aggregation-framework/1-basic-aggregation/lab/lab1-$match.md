# Lab 
Please navigate to the m121 directory from your terminal and then connect to the class Atlas cluster through the mongo shell using the following connection string:

> mongo "mongodb://cluster0-shard-00-00-jxeqq.mongodb.net:27017,cluster0-shard-00-01-jxeqq.mongodb.net:27017,cluster0-shard-00-02-jxeqq.mongodb.net:27017/aggregations?replicaSet=Cluster0-shard-0" --authenticationDatabase admin --ssl -u m121 -p aggregations --norc

After connecting to the cluster, ensure you can see the movies collection by typing show collections and then run the command db.movies.findOne(). Take a moment to familiarize yourself with the schema.

## Problem:

Help MongoDB pick a movie our next movie night! Based on employee polling, we've decided that potential movies must meet the following criteria.

- `imdb.rating` is at least 7 (Giá trị `imdb.rating` lớn hơn hoặc bằng 7)
- `genres` does not contain "Crime" or "Horror" (Giá trị trường `genres` không chứa "Crime" và "Horror")
- `rated` is either "PG" or "G" (Giá trị trường `rated` chứa "PG" hoặc "G")
- `languages` contains "English" and "Japanese" (Giá trị trường `languages` phải có 2 giá trị "English" và "Japanese")
Assign the aggregation to a variable named pipeline, like:


    ```js
    var pipeline = [ { $match: { ... } } ]
    ```

## Solution
<details>
<summary>Xem chi tiết</summary>

- `imdb.rating` is at least 7

    => sử dụng `$gte`
    - Định nghĩa: selects the documents where the value of the field is greater than or equal to (i.e. >=) a specified value
    - Cú pháp
    > { field: {    $gte:   value} }
```js
{
    $gte: {
        "imdb.rating": 7
    }
}
```
-  `genres` does not contain "Crime" or "Horror"
    - Định nghĩa: selects the documents where:
        - the field value is not in the specified array or
        - the field does not exist.
    => Sử dụng `$nin`
    - Cú pháp
    > { field: {    $nin:   [value1, value2, ....]} }
```js
{
    genres: {
        $nin: ["Crime","Horror"]
    }
}
```
-  `rated` is either "PG" or "G"

    => Sử dụng `$in`
    - Định nghĩa: Selects the documents where the value of a field equals any value in the specified array
    - Cú pháp
    > { field: {    $in:   [value1, value2, ....]} }
```js
{
    languages: {
        $in: ["PG","G"]
    }
}
```
- `languages` contains "English" and "Japanese"

    => Sử dụng `$all`
    - Định nghĩa: The `$all` operator selects the documents where the value of a field is an array that contains all the specified elements
```js    
{
    languages: {
        $all: ["English","Japanese"]
    }
}
```
Cuối cùng chúng ta có kết quả sau
```js
var pipeline = [
  {
    $match: {
      "imdb.rating": { $gte: 7 },
      genres: { $nin: [ "Crime", "Horror" ] } ,
      rated: { $in: ["PG", "G" ] },
      languages: { $all: [ "English", "Japanese" ] }
    }
  }
]
```
</details>

## Result
<details >
<summary>Xem chi tiết</summary>
    
    15
</details>