

# Content of Table
## flatMap vs map
- map() transformation is used to transform the data into different values, types by returning the same number of records.
- flatMap() transformation is used to transform from one record to multiple records.

```python
documents = spark.sparkContext.parallelize([
    (1, "the shawshank redemption"),
    (2, "the godfather"),
    (3, "the godfather part two")
], 2)

documents\
    .map(lambda docid_and_title: extract_words(docid_and_title))\
    .collect()

[[('the', 1), ('shawshank', 1), ('redemption', 1)],
 [('the', 1), ('godfather', 1)],
 [('the', 1), ('godfather', 1), ('part', 1), ('two', 1)]]
```

```python
documents\
    .flatMap(lambda docid_and_title: extract_words(docid_and_title))\
    .collect()

[('the', 1),
 ('shawshank', 1),
 ('redemption', 1),
 ('the', 1),
 ('godfather', 1),
 ('the', 1),
 ('godfather', 1),
 ('part', 1),
 ('two', 1)]
```