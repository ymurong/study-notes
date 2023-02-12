- [Table of Content](#table-of-content)
  - [turn dataframe to list of tuples](#turn-dataframe-to-list-of-tuples)
  - [tuple to dict in sorted order](#tuple-to-dict-in-sorted-order)


# Table of Content
## turn dataframe to list of tuples
- itertuples

Iterate over DataFrame rows as namedtuples. unnamedtuples when name = None
```python
for row in df.itertuples(index=False, name=None):
    print(row)

Pandas(num_legs=4, num_wings=0)
Pandas(num_legs=2, num_wings=2)
```

## tuple to dict in sorted order
- sorted
```python
wordcount_dict = dict(sorted(
        list_of_tuples,
        key=lambda x: x[1], # based on 2nd value
        reverse=True # Desc
    ))
```