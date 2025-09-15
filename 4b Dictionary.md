# Dictionaries in Python   

# 1a Create dictionary of your choice of keys and values. Create dictionary size of 10 elements.  

``` python
# 1a
my_dict = {
    "Name": "Alice",
    "Age": 25,
    "City": "New York",
    "Country": "USA",
    "Occupation": "Engineer",
    "Company": "TechCorp",
    "Email": "alice@example.com",
    "Phone": "123-456-7890",
    "Salary": 70000,
    "Department": "R&D"
}
print(my_dict)
```

# 1b
```python
# 1b
my_user_dict = {}

while True:
    key = input("Enter key: ")
    value = input("Enter value: ")
    my_user_dict[key] = value
    
    cont = input("Do you want to continue (Y/N)? ")
    if cont.lower() == "n":
        break

print("Final dictionary:", my_user_dict)
```

# 1c

``` python
# 1c
data = [
    ('Name', 'Sarah Connor'),
    ('Date of birth', '1 Jan 1980'),
    ('Address', '1000 Black Mountain Drive'),
    ('Zip', 92126),
    ('Name', 'Jim Hawkins')
]

my_dict = {}
for key, value in data:
    if key in my_dict:
        print(f"Duplicate key found: {key}. Please change the key.")
    else:
        my_dict[key] = value

print("Final dictionary:", my_dict)
```

# 1d
``` python
# 1d
my_list = ["a", 1, "b", 2, "c", 3, "d", 4]
my_dict = {}

for i in range(0, len(my_list), 2):
    my_dict[my_list[i]] = my_list[i+1]

print("Converted dictionary:", my_dict)
```

# 1 e

```python
# 1e
text = """The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia.
It has
```

# 2a

```python
# 2a
d_orig = {123: "Coconut"}
d_copy = d_orig.copy()   # create an independent copy

d_copy[123] = "Mango"

print("Original dictionary:", d_orig)
print("Copied dictionary:", d_copy)

```

# 2b
If we use d_copy = d_orig, both variables point to the same dictionary object, so changing one affects the other.

# 2c
``` python
# 2c
my_dict = {["a", "b"]: "value"}   # This will raise: TypeError: unhashable type: 'list'
```

#Challenge 
This exercise challenged me in understanding how dictionary keys must be unique and immutable. I initially struggled with handling duplicate keys and realizing that the latest value overwrites the previous one. Troubleshooting also helped me learn that assigning one dictionary to another (d_copy = d_orig) links them together, which was initially confusing. Finally, it was tricky to understand why lists cannot be used as keys, but I learned that keys must be hashable.
