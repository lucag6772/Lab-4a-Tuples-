# Lab-4a-Tuples-

# Excercising tuples 

# 1a

```python 
# 1a
my_tuple = tuple(input(f"Enter element {i+1}: ") for i in range(5))
print("My tuple:", my_tuple)
```

# 1b

```python
# 1b
my_tuple = (10, 20, 30, 40, 50)
temp_list = list(my_tuple)
temp_list[2] = 99  
my_tuple = tuple(temp_list)
print("Modified tuple:", my_tuple)
```

# 1c  

```python
# 1c
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
counts = {}
for num in my_tuple:
    counts[num] = counts.get(num, 0) + 1
print("Element counts:", counts)
```

# 1d

``` python
# 1d
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
print("Original tuple id:", id(my_tuple))

my_tuple = my_tuple + my_tuple
print("New tuple id:", id(my_tuple))
```

# 1e

``` python
x = (1,2,3,4)
x.append(1)   # Not allowed, tuples don’t have append
x[1] = "hello"  # Not allowed, items cannot be reassigned
del x[2]      # Not allowed, items cannot be deleted
```

# 2a

``` python
(one, two, three, four) = (1, 2, 3, 4)
print(type(one), type(two), type(three), type(four))
```

# 2b 

``` python
x = (1, 2, 3, 4)
a, b, *c = x
print(a, b, c)   # Output: 1 2 [3, 4]

```

# 2c

``` python
# 2c
x = (1, 2, 3, 4)
a, *b, c = x
print(a, b, c)   # Output: 1 [2, 3] 4
```

# 3

``` python
my_x = [100,200,300,400]
my_y = (200,300,400,500)

print("List addresses:")
for i, val in enumerate(my_x):
    print(f"Index {i}: value={val}, id={id(val)}")

print("\nTuple addresses:")
for i, val in enumerate(my_y):
    print(f"Index {i}: value={val}, id={id(val)}")
```

# Management Results

List (my_x = [100,200,300,400])

Index	Value	Address (id)
0	100	139276936017960
1	200	139276936021160
2	300	139276852241280
3	400	139276852240832

Tuple (my_y = (200,300,400,500))

Index	Value	Address (id)
0	200	139276936021160
1	300	139276852240800
2	400	139276852240576
3	500	139276852242720

# challenges 
This exercise was particularly challenging in terms of understanding immutability of tuples. At first, it was hard to understand why operations like append or reassignment don't work. Getting proficient in unpacking with * also needed much practice. The hardest part here was memory management; I was least expecting that what would happen if Python reused memory addresses between lists and tuples, though this again helped me understand memory conservation in Python.

