---
title: Querying Users
category: REST APIs
category-order: 3
order: 2
---


You can query users via the API using query parameters that can be used to filter, sort, and paginate the response. 


#### Example

The following query simply queries for a user with a userName = bjensen@example.com

```
curl -X GET \
https://api-TENANT-NAME.forgeblocks.com/v1/users?filter=userName%20eq%20%22bjensen@example.com%22 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer ACCESS_TOKEN' \
-H 'cache-control: no-cache' \
```

### Parameters and Filtering

There are a lot more ways you can query the users. These parameters and filters are available for you to pass in when querying for results.

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
**filter** | The query you want to filter by.
**startIndex** | The 0-based index of the first query result.                     |
**count** | Maximum number of query results. eg: 10. 
**fields** | Fields to return from the query.
**sortBy** | The attribute you want to sort by.



### Operators

You can user operators to further refine your results. The actual comparison is dependent on the attribute type. For string attribute types, this is a lexicographical comparison and for DateTime types, it is a chronological comparison.

Operator | Definition | Description |
|--------|-------------|--------|
**eq** | equal | The attribute and operator values must be identical for a match.
**co** | contains | The entire operator value must be a substring of the attribute value for a match.
**sw** | starts with | The entire operator value must be a substring of the attribute value, starting at the beginning of the attribute value. This criterion is satisfied if the two strings are identical.
**pr** | present (has value) | If the attribute has a non-empty value, or if it contains a non-empty node for complex attributes there is a match.
**gt** | greater than | If the attribute value is greater than operator value, there is a match. The actual comparison is dependent on the attribute type. For string attribute types, this is a lexicographical comparison and for DateTime types, it is a chronological comparison.
**ge** | greater than or equal | If the attribute value is greater than or equal to the operator value, there is a match. The actual comparison is dependent on the attribute type. For string attribute types, this is a lexicographical comparison and for DateTime types, it is a chronological comparison.
**lt** | less than | If the attribute value is less than operator value, there is a match. The actual comparison is dependent on the attribute type. For string attribute types, this is a lexicographical comparison and for DateTime types, it is a chronological comparison.
**le** | less than or equal | If the attribute value is less than or equal to the operator value, there is a match. The actual comparison is dependent on the attribute type. For string attribute types, this is a lexicographical comparison and for DateTime types, it is a chronological comparison.
**!**  | not expression | The attribute must not equal the operator value.
**_fields** | result fields | The fields to return in the result.



<br>


