---
title: Querying Users
category: REST APIs
category-order: 3
order: 2
---


You can query users via the API with query parameters that filter, sort, and paginate the response. 


#### Example

The following query filters for a user named *bjensen@example.com*

```
curl -X GET \
https://api-TENANT-NAME.forgeblocks.com/v1/users?filter=userName%20eq%20%22bjensen@example.com%22 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer ACCESS_TOKEN' \
-H 'cache-control: no-cache' 
```

### Parameters and Filtering

You can use parameters such as **filter** to search for users.

#### Examples

```
filter=userName eq "bjensen"
filter=name/familyName co "O'Malley"
filter=userName sw "J"
filter=title pr
filter=title pr and userType eq "Employee"
```

| Parameter |  Description |
|--------|-------------|
**filter** | The query to filter by.
**startIndex** | The 0-based index of the first query result.                     |
**count** | Maximum number of query results. 
**fields** | Fields to return from the query.
**sortBy** | Attribute to sort by.



### Comparators

You can use comparators to further refine your results, depending on attribute type. 
String attribute types result in a lexicographical comparison. DateTime types
result in a chronological comparison.

For comparators, use *json-pointer* *comparator*  *json-value*, where the comparator
 is one of the following:
 
* *eq* (equals)
* *co* (contains)
* *sw* (starts with)
* *lt* (less than)
* *le* (less than or equal to)
* *gt* (greater than)
* *ge* (greater than or equal to)

For presence, use *json-pointer* *pr* to match resources where:

* The JSON pointer is present
* The value it points to is not *null*

Literal values include true (match anything) and false (match nothing).

Complex expressions employ *and*, *or*, and *!* (not), with parentheses (expression), to group expressions.
    
<br>


