- [Table of Content](#table-of-content)
  - [tuple to dict in sorted order](#tuple-to-dict-in-sorted-order)



# Table of Content
## tuple to dict in sorted order
- sorted
```python
wordcount_dict = dict(sorted(
        list_of_tuples,
        key=lambda x: x[1], # based on 2nd value
        reverse=True # Desc
    ))
```