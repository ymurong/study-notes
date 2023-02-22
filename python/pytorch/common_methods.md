- [Content of Table](#content-of-table)
  - [torch.mul vs torch.mm](#torchmul-vs-torchmm)
  - [torch squeeze](#torch-squeeze)

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

## torch squeeze

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