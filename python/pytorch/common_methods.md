- [Content of Table](#content-of-table)
  - [torch.mul vs torch.mm](#torchmul-vs-torchmm)
  - [torch.matmul vs torch.bmm](#torchmatmul-vs-torchbmm)
    - [torch.bmm](#torchbmm)
    - [torch.matmul(input, other): more flexible](#torchmatmulinput-other-more-flexible)
  - [torch squeeze \& unsqueeze](#torch-squeeze--unsqueeze)
  - [torch cat vs stack](#torch-cat-vs-stack)

# Content of Table

## torch.mul vs torch.mm
- torch.mul(a, b)是矩阵a和b对应位相乘，比如a的维度是(1, 2)，b的维度是(1, 2)，返回的仍是(1, 2)的矩阵
- torch.mm(a, b)是矩阵a和b矩阵相乘，比如a的维度是(1, 2)，b的维度是(2, 3)，返回的就是(1, 3)的矩阵
```python
import torch

a = torch.rand(1, 2)
b = torch.rand(1, 2)
print(torch.mul(a, b))  # 返回 1*2 的tensor

b = torch.rand(2, 3)
print(torch.mm(a, c))   # 返回 1*3 的tensor
```



## torch.matmul vs torch.bmm


### torch.bmm
batch matrix multiplication with strictions on the shape of matrix

```python
a = torch.rand(b, 5, 1)
b = torch.rand(b, 1, 5)
print(torch.bmm(a,b))  # 返回 b*5*5 的tensor
```

### torch.matmul(input, other): more flexible 

- (same input&other:1D) -> dot product
- (input: 2D, other: 2D) -> matrix multiplication
- (input&other:3D/4D) -> can do bmm or even more flexible bmm

```python
a = torch.rand(b, l, 5, 1)
b = torch.rand(b, l, 1, 5)
print(torch.matmul(a,b))  # 返回 b*l*5*5 的tensor
```

- (input: 2D, other:1D): can broadcast other, then dot product over 
  
```python selected dimension 
a = torch.rand(4,3)
b = torch.rand(3)
# -> (4,3) @ (3,4)
# -> (4,4) -> dot product
# -> (4)
print(torch.matmul(a,b))  # 返回 (4) 的tensor
```
- (input: 1D, other:2D): can add dimension to input, matrix multiplication then remove added dimension
```python
a = torch.rand(4)
b = torch.rand(4,3)
# -> (1,4) @ (4,3)
# -> (1,3) -> remove added dimension
# -> (3)
print(torch.matmul(a,b))  # 返回 (3) 的tensor
```
- (input: 1D, other:3D or more): a batched matrix multiply
```python
a = torch.rand(3)
b = torch.rand(2,3,4)
# -> (3) -> (2,1,3)
# ->  (2,1,3) * (2,3,4)
# -> (2,1,4) -> remove added dimension
# -> (2,4)
print(torch.matmul(a,b))  # 返回 (2,4) 的tensor
```

- (input: 3D or more, other:1D): dot product on given dimension
```python
a = torch.rand(2,3,4)
b = torch.rand(4)
# -> (4) * (2,3,4)
# ->  (2,3,4) * (2,3,4) -> dot product on (3,4)
# -> (2,3)
print(torch.matmul(a,b))  # 返回 (2,4) 的tensor
```
- (input: 4D or more, other:3D): if broadcast possible then batch matrix multiply
```python
a = torch.rand(10,1,2,4)
b = torch.rand(2,4,5)
# -> (10,1,2,4) ->  (10,2,2,4) # broadcast
# -> (10,2,2,4) * (10,2,4,5) mm on 3rd and 4th dim
# -> (10,2,2,5)
print(torch.matmul(a,b))  # 返回 (10,2,2,5) 的tensor
```
- also check the following documentation
[about matmul and bmm](https://blog.csdn.net/foneone/article/details/103876519)

## torch squeeze & unsqueeze

torch.squeeze(input, dim=None) 

Returns a tensor with all the dimensions of input of size 1 removed.

- if input is of shape (A x 1 x B x C x 1 x D), then the output tensor will be of shape (A x B x C x D)
- When dim is given, a squeeze operation is done only in the given dimension. If input is of shape: (A×1×B), squeeze(input, 0) leaves the tensor unchanged, but squeeze(input, 1) will squeeze the tensor to the shape (AxB)

```python
import torch

a = torch.rand(A, 1, B, C, 1, D)
print(torch.squeeze(a))  # 返回 (A x B x C x D)

b = torch.rand(A, 1, B)
print(torch.squeeze(b, dim=0))   # 返回 (A x 1 x B)
print(torch.squeeze(b, dim=1))   # 返回 (A x B)
```

## torch cat vs stack
- torch.cat: Concatenates the given sequence of seq tensors in the given dimension. All tensors must either have the same shape (except in the concatenating dimension) or be empty.

```python
a = torch.rand(3,4)
b = torch.rand(3,4)
print(torch.cat((a,b), dim=0)) # 返回 (6x4)
```

- torch.stack: Concatenates sequence of tensors along a new dimension.

```python
a = torch.rand(3,4)
b = torch.rand(3,4)
print(torch.stack((a,b), dim=0)) # 返回 (2x3x4)
```