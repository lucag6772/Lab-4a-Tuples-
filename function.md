# Functions

# 1a) Convert kilometers per liter (kpl) ↔ miles per gallon (mpg)  

Conversion factors:  
- **1 kpl ≈ 2.35215 mpg**  
- **1 mpg ≈ 0.42514 kpl**  

```python
def convert_kpl_to_mpg(*values):
    return [v * 2.35215 for v in values]

def convert_mpg_to_kpl(*values):
    return [v * 0.42514 for v in values]

while True:
    choice = input("Convert from (1) kpl to mpg or (2) mpg to kpl? (Q to quit): ")
    if choice.lower() == "q":
        break

    numbers = input("Enter values separated by space: ").split()

    # Input validation
    try:
        numbers = [float(num) for num in numbers]
    except ValueError:
        print("Error: Please enter numeric values only.")
        continue

    if choice == "1":
        result = convert_kpl_to_mpg(*numbers)
        print("Converted to mpg:", result)
    elif choice == "2":
        result = convert_mpg_to_kpl(*numbers)
        print("Converted to kpl:", result)
    else:
        print("Invalid option. Please choose 1, 2, or Q.")

```

# 1b

```python 
def print_reverse(*args):
    for val in reversed(args):
        print(val)

print_reverse(1, 2, 3, 4, 5)   # Output: 5 4 3 2 1
```

# 1c

``` python
# 1c
def modify_list(lst):
    lst.append(100)  # This changes the original list outside the function
    print("Inside function:", lst)

my_list = [1, 2, 3]
modify_list(my_list)
print("Outside function:", my_list)   # Change is visible

def safe_modify_list(lst):
    lst = lst.copy()  # Work on a copy
    lst.append(200)
    print("Inside safe function:", lst)

safe_modify_list(my_list)
print("Outside after safe function:", my_list)  # Original is unchanged
```

# 1d 

``` python 
x = 5

def funct_1():
    x = 3   # Local variable, does not change global x

def funct_2():
    global x
    x = 2   # Modifies global x

funct_1()
print("After funct_1, x =", x)  # Still 5

funct_2()
print("After funct_2, x =", x)  # Now 2

```

# 2

``` python
# origional

def my_func(a,b,**c):
  print(c)

my_func(1,2,3,4,5,6)

# fix Use *args to collect extra positional arguments.

def my_func(a, b, *c):
    print(c)

my_func(1, 2, 3, 4, 5, 6)   # Output: (3, 4, 5, 6)

```

# challenge 
This assignment posed some difficulties for me. It was challenging to code the unit conversion program, as I had to validate input while simultaneously accepting multiple arguments. I also had to research the correct conversion factors to make sure the arithmetic was accurate. Another problem was understanding why altering mutable objects, such as lists or dictionaries, passed into functions can have side effects outside of the function, and this helped me understand the importance of using copies when necessary. Finally, working with global variables and processing keyword arguments versus positional arguments taught me more about Python's behavior regarding function scope and parameters.
