# query_iterator()

This method conducts a query with an iterator.

## Invocation

```python
query_iterator(expr, output_fields, limit, consistency_level)
```

## Parameters

| Parameter | Description | Type | Required |
| --- | --- | --- | --- |
| `expr` | 	Boolean expression to filter the data. | String | True |
| `output_fields` | Name of the field to return. | list[String] | False |
| `limit` | Number of results to return per page. | Integer | True |
| `consistency_level` | Consistency level used in the search. Find more expression details in [query()](query().md). | String/Integer | False |

## Return

A list that contains all results.

## Raises

- `RpcError`: error if gRPC encounter an error.
- `ParamError`: error if the parameters are invalid.
- `DataTypeNotMatchException`: error if wrong type of data is passed to server.
- `BaseException`: error if the return result from server is not ok.

## Example

```python
# filter books with the number of pages ranging from 600 to 700
expr = "600 <= num_pages <= 700"

# return `bookID` and `authors`
output_fields=[bookID, authors]

# return 5 results per page
limit = 5

# create a query iterator
query_iterator = collection.query_iterator(expr, output_fields, limit)

while True:
    # turn to the next page
    res = query_iterator.next()
    if len(res) == 0:
        print("query iteration finished, close")
        # close the iterator
        query_iterator.close()
        break
    for i in range(len(res)):
        print(res[i])
```