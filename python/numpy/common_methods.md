


# Content of Table
## np.stack
Join a sequence of arrays along a new axis.
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

np.stack((a, b), axis=1)
array([[1, 4],
       [2, 5],
       [3, 6]])

np.stack((a, b), axis=1).shape
(3,2)
```