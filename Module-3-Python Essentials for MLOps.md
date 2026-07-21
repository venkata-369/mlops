### Lab 1: Variables

```python
# Variables

name = "Venkat"
age = 30
salary = 65000.50
is_employee = True

print(name)
print(age)
print(salary)
print(is_employee)
```

---

### Lab 2: Data Types

```python
# Data Types

name = "Venkat"          # String
age = 30                 # Integer
salary = 65000.50        # Float
is_active = True         # Boolean

print(type(name))
print(type(age))
print(type(salary))
print(type(is_active))
```

---

### Lab 3: Operators

```python
a = 20
b = 5

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", a / b)
print("Modulus:", a % b)
print("Power:", a ** b)
```

Comparison Operators

```python
print(a > b)
print(a < b)
print(a == b)
print(a != b)
```

---

### Lab 4: Functions

```python
def greet(name):
    print("Welcome", name)

greet("Venkat")
```

Function with Return

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

---

### Lab 5: Lists

```python
fruits = ["Apple", "Banana", "Orange"]

print(fruits)

print(fruits[0])

fruits.append("Mango")

print(fruits)
```

Loop through List

```python
for fruit in fruits:
    print(fruit)
```

---

### Lab 6: Tuples

```python
colors = ("Red", "Green", "Blue")

print(colors)

print(colors[1])
```

---

### Lab 7: Dictionaries

```python
customer = {
    "id": 101,
    "name": "Venkat",
    "city": "Hyderabad"
}

print(customer)

print(customer["name"])
```

Loop Dictionary

```python
for key, value in customer.items():
    print(key, ":", value)
```

---

### Lab 8: Loops

For Loop

```python
for i in range(1, 6):
    print(i)
```

While Loop

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

---

### Lab 9: Conditional Statements

```python
marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
else:
    print("Grade C")
```

---

### Lab 10: Hands-on Lab

Employee Details

```python
employee = {
    "ID":101,
    "Name":"Venkat",
    "Department":"Database",
    "Salary":80000
}

print(employee)
```

Increase Salary

```python
employee["Salary"] += 5000

print(employee)
```

---

### Lab 11: Read CSV

Create a file named **customers.csv**

```csv
CustomerID,Name,City,Age
101,Venkat,Hyderabad,30
102,Ravi,Bangalore,28
103,Sneha,Chennai,27
104,Asha,Pune,35
```

Python Code

```python
import pandas as pd

df = pd.read_csv("customers.csv")

print(df)
```

---

### Lab 12: Print Customer Records

Print All Records

```python
import pandas as pd

df = pd.read_csv("customers.csv")

print(df)
```

Print Customer Names

```python
print(df["Name"])
```

Print First Customer

```python
print(df.iloc[0])
```

Print Customer by ID

```python
customer = df[df["CustomerID"] == 102]

print(customer)
```

Loop Through Records

```python
for index, row in df.iterrows():
    print(row["CustomerID"], row["Name"], row["City"])
```

---

### Mini Practice Exercise

Create a file named **employees.csv**

```csv
EmpID,Name,Department,Salary
1,Venkat,Database,80000
2,Ravi,DevOps,75000
3,Priya,Cloud,90000
4,John,Python,70000
5,Asha,AI,95000
```

Tasks:

1. Read the CSV file.
2. Print all employees.
3. Print only the `Name` column.
4. Print employees with salary greater than 80,000.
5. Print employees in the `Cloud` department.
6. Calculate the average salary.
7. Find the highest-paid employee.
8. Sort employees by salary (highest first).
9. Add a new column called `Bonus` (10% of salary).
10. Save the updated data as `employees_new.csv`.


