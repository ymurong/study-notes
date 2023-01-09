# Table of Contents
- [Table of Contents](#table-of-contents)
  - [1 Basic Relationship Patterns](#1-basic-relationship-patterns)
    - [1.1 Difference between back\_populates and backref](#11-difference-between-back_populates-and-backref)



## 1 Basic Relationship Patterns

### 1.1 Difference between back_populates and backref

backref is a shortcut for configuring both parent.children and child.parent relationships at one place only on the parent or the child class (not both). That is, instead of having

```python
children = relationship("Child", back_populates="parent")  # on the parent class
```
and

```python
parent = relationship("Parent", back_populates="children")  # on the child class
```

you only need one of this:

```python
children = relationship("Child", backref="parent")  # only on the parent class
```
or

```python
parent = relationship("Parent", backref="children")  # only on the child class
```

If you use back_populates, it needs to go on both parent and child classes. If you use backref, it needs to go on one of them only. back_populates informs each relationship about the other, so that they are kept in sync. 
