# Introduction to Programming Concepts: Identifiers, Variables, Containers, Functions, and Objects

## Overview

Programming is more than writing instructions that tell a computer what to do. It also involves organizing information, structuring instructions, and designing software in a way that makes it understandable, reusable, and maintainable.

Before developing complex applications, developers need to understand several fundamental programming concepts. These concepts provide the foundation for understanding programming languages, software architecture, and application development.

In this lesson, I explored four important areas:

1. Identifiers: Variables and Constants
2. Containers: Arrays and Vectors
3. Functions and Modular Programming
4. Objects and Object-Oriented Programming (OOP)

This document explains these concepts using Python examples and practical scenarios from backend development.

---

## 1. Identifiers: Variables and Constants

### What Are Identifiers?

An identifier is a name used to identify and reference a programming element, such as a variable, constant, function, or class.

Identifiers allow developers to interact with program components using meaningful names instead of directly referring to their underlying memory locations.

For example:

```python
username = "Mostafa"
age = 25
```

In this example:

- `username` is an identifier.
- `age` is an identifier.
- `"Mostafa"` and `25` are the associated values.

Meaningful identifiers improve readability and make code easier to maintain.

Compare:

```python
x = 500
y = 2
z = x * y
```

With:

```python
product_price = 500
quantity = 2
total_price = product_price * quantity
```

The second example communicates the purpose of each value more clearly.

### Variables

A variable is a named reference to a value that can change during program execution.

Variables are essential because applications constantly work with changing information, including user input, product quantities, prices, authentication states, and database results.

Example:

```python
user_balance = 1000

user_balance = 750

user_balance = 500
```

The value associated with `user_balance` changes throughout execution.

In backend development, variables can represent information such as:

- The currently authenticated user.
- The number of products in a shopping cart.
- The total price of an order.
- The result of a database query.
- Information received from an API request.

### Constants

A constant is a named value intended to remain unchanged during program execution.

Constants are particularly useful for values that represent application rules, configuration settings, or fixed parameters.

Example:

```python
TAX_RATE = 0.14
MAX_LOGIN_ATTEMPTS = 5
STORE_NAME = "Tech Store"
```

Using constants improves maintainability because developers can define important values in one place instead of repeatedly writing the same values throughout the application.

For example:

```python
TAX_RATE = 0.14

product_price = 1000

tax = product_price * TAX_RATE
total_price = product_price + tax
```

If the tax rate changes, we only need to update its definition.

**Python consideration:** Python does not enforce constants at the language level. Uppercase naming is a convention that communicates that a value should not be reassigned.

### Variables vs. Constants

| Feature           | Variables             | Constants              |
| ----------------- | --------------------- | ---------------------- |
| Purpose           | Store changing values | Represent fixed values |
| Modification      | Expected              | Should be avoided      |
| Naming convention | `user_name`           | `MAX_USERS`            |
| Example           | `quantity = 5`        | `TAX_RATE = 0.14`      |

---

## 2. Containers: Arrays and Vectors

### What Are Containers?

Containers are data structures that store and organize multiple values within a single structure.

Without containers, developers might need to create individual variables for every element.

For example:

```python
product_1 = "Laptop"
product_2 = "Mouse"
product_3 = "Keyboard"
```

This approach becomes difficult to maintain when dealing with large collections of data.

Containers solve this problem by grouping related values together.

Common container types include arrays, vectors, lists, tuples, sets, and dictionaries.

### Arrays

An array is a data structure that stores multiple elements in an ordered sequence.

Traditional arrays generally have the following characteristics:

- Elements are stored in contiguous memory locations.
- Elements are accessed through indexes.
- The array has a fixed capacity.
- In statically typed languages, elements generally share the same data type.

Example of an array-like collection:

```python
product_prices = [100, 250, 500, 750]

print(product_prices[0])
print(product_prices[2])
```

Output:

```text
100
500
```

Indexes typically start at zero, meaning the first element is accessed using index `0`.

**Python distinction:** Python's built-in `list` is dynamically resizable, not a traditional fixed-size array. Python also provides the `array` module for specialized typed arrays.

### Vectors

A vector is a dynamic array-like container that can grow or shrink as elements are added or removed.

For example, C++ provides `std::vector`, which automatically manages its storage capacity.

In Python, the built-in list provides similar dynamic-array behavior.

```python
cart = ["Laptop", "Mouse"]

cart.append("Keyboard")

print(cart)
```

Output:

```text
['Laptop', 'Mouse', 'Keyboard']
```

The collection grows without requiring the developer to manually allocate a larger container.

### Arrays vs. Vectors

| Feature         | Traditional array   | Dynamic vector                  |
| --------------- | ------------------- | ------------------------------- |
| Size            | Fixed capacity      | Resizable                       |
| Memory          | Often predictable   | May reserve additional capacity |
| Indexed access  | O(1)                | O(1)                            |
| Adding elements | Limited by capacity | Can grow dynamically            |
| Flexibility     | Less flexible       | More flexible                   |

An important performance consideration is that vectors do not inherently have slower indexed access than arrays. Both typically provide constant-time indexed access, O(1).

However, vectors can use additional memory for reserved capacity and occasionally require reallocation when their capacity is exceeded.

### Backend Development Connection

Backend applications frequently process collections of data.

For example, a Django application might retrieve products using:

```python
products = Product.objects.all()
```

This returns a Django QuerySet rather than an array or vector.

A QuerySet is a Django-specific abstraction that represents a database query and can be evaluated lazily.

Understanding containers makes it easier to understand how applications manage collections of database records and API data.

---

## 3. Functions and Modular Programming

### What Is a Function?

A function is a reusable block of code designed to perform a specific task.

Functions allow developers to divide complex programs into smaller, manageable components.

A function can:

1. Receive input.
2. Process the input.
3. Return a result.

Example:

```python
def calculate_total(price, quantity):
    total = price * quantity
    return total
```

Calling the function:

```python
result = calculate_total(500, 2)

print(result)
```

Output:

```text
1000
```

### Understanding Function Components

- `def`: Python keyword used to define a function.
- `calculate_total`: Function name.
- `price` and `quantity`: Parameters.
- `total`: A variable holding the calculated value.
- `return`: Sends a result back to the caller.

### Parameters vs. Arguments

Parameters and arguments are related but represent different things.

Parameters are names defined in the function declaration.

Arguments are actual values passed when calling the function.

```python
def greet(name):
    return f"Hello, {name}"

greet("Mostafa")
```

Here:

- `name` is a parameter.
- `"Mostafa"` is an argument.

### Types of Functions

**Built-in functions**

These are provided by the programming language.

Examples:

```python
print("Hello World")

len("Programming")

max(10, 20, 30)

sum([10, 20, 30])
```

**User-defined functions**

These are created by developers to solve specific problems.

```python
def calculate_discount(price, discount_percentage):
    discount = price * (discount_percentage / 100)
    return price - discount


final_price = calculate_discount(1000, 10)

print(final_price)
```

Output:

```text
900.0
```

### Modular Programming

Modular programming is an approach that divides a large program into smaller, organized components.

Functions support this methodology by allowing developers to separate responsibilities.

Consider an e-commerce application:

```text
E-commerce Application
│
├── User Management
│   ├── register_user()
│   ├── authenticate_user()
│   └── update_profile()
│
├── Product Management
│   ├── create_product()
│   ├── get_product()
│   └── update_product()
│
└── Order Management
    ├── create_order()
    ├── calculate_total()
    └── process_payment()
```

Benefits include:

- Reusability.
- Maintainability.
- Readability.
- Testability.
- Better organization.

### Functions in Django

Django supports function-based views, where a function receives an HTTP request and returns an HTTP response.

```python
from django.http import JsonResponse

def product_list(request):
    products = [
        {"id": 1, "name": "Laptop"},
        {"id": 2, "name": "Mouse"},
    ]

    return JsonResponse({"products": products})
```

This demonstrates how functions connect application logic with incoming HTTP requests.

---

## 4. Objects and Object-Oriented Programming

### What Is Object-Oriented Programming?

Object-Oriented Programming (OOP) is a programming paradigm that organizes software around objects.

An object combines data and behavior.

- Data is represented through attributes or properties.
- Behavior is represented through methods.

This approach helps developers model entities and their interactions within an application.

### Classes and Objects

A class is a blueprint that defines the structure and behavior of objects.

An object is an individual instance created from a class.

Consider an e-commerce product.

A product might have:

**Attributes:**

- Name.
- Price.
- Description.
- Stock quantity.

**Methods:**

- Check availability.
- Update price.
- Reduce stock.
- Calculate discount.

Python implementation:

```python
class Product:
    def __init__(self, name, price, stock):
        self.name = name
        self.price = price
        self.stock = stock

    def is_available(self):
        return self.stock > 0

    def update_price(self, new_price):
        self.price = new_price
```

### Understanding the Class

`class Product:` defines a class named `Product`.

`__init__` is a special initialization method that runs when an object is created.

`self` refers to the current instance.

The assignments:

```python
self.name = name
self.price = price
self.stock = stock
```

Initialize the object's attributes.

The `is_available()` and `update_price()` methods define behaviors associated with the product.

### Creating Objects

```python
laptop = Product("Laptop", 15000, 10)

mouse = Product("Mouse", 500, 0)
```

Both objects use the same class but contain different information.

We can interact with them:

```python
print(laptop.name)
print(laptop.is_available())

print(mouse.name)
print(mouse.is_available())
```

Output:

```text
Laptop
True
Mouse
False
```

### Procedural Programming vs. OOP

Procedural programming organizes software around procedures and functions.

OOP organizes software around objects that combine related data and behavior.

Procedural example:

```python
product_price = 1000
product_stock = 10

def check_stock(stock):
    return stock > 0

print(check_stock(product_stock))
```

Object-oriented example:

```python
class Product:
    def __init__(self, price, stock):
        self.price = price
        self.stock = stock

    def check_stock(self):
        return self.stock > 0


product = Product(1000, 10)

print(product.check_stock())
```

Neither approach is universally better. The choice depends on the problem, application requirements, and design considerations.

### Four Fundamental OOP Principles

**1. Encapsulation**

Combines related data and behavior while controlling access to an object's internal state.

**2. Abstraction**

Hides unnecessary implementation details and exposes essential functionality.

**3. Inheritance**

Allows one class to reuse or extend the functionality of another class.

**4. Polymorphism**

Allows different objects to respond to the same interface or method call in different ways.

These principles help developers design more flexible and maintainable software systems.

### OOP in Django

Django uses OOP extensively.

For example:

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=200)
    price = models.DecimalField(
        max_digits=10,
        decimal_places=2
    )
    stock = models.IntegerField(default=0)

    def is_available(self):
        return self.stock > 0
```

In this example:

- `Product` is a class.
- Each database record corresponds to a model instance.
- `name`, `price`, and `stock` are model fields.
- `is_available()` is a method.

Django models demonstrate how OOP concepts can be applied to real backend applications.

---

## 5. Connecting All Concepts: An E-commerce Example

These concepts become more meaningful when used together.

Consider a simplified e-commerce application that calculates the total price of products in a shopping cart.

```python
TAX_RATE = 0.14


class Product:
    def __init__(self, name, price, stock):
        self.name = name
        self.price = price
        self.stock = stock


def calculate_total(cart):
    subtotal = sum(
        product.price for product in cart
    )

    tax = subtotal * TAX_RATE

    return subtotal + tax


laptop = Product("Laptop", 15000, 5)
mouse = Product("Mouse", 500, 10)

cart = [laptop, mouse]

total = calculate_total(cart)

print(total)
```

Output:

```text
17670.0
```

This example combines:

- **Identifiers:** Names such as `TAX_RATE`, `cart`, and `total`.
- **Constants:** The tax rate.
- **Containers:** The list storing product objects.
- **Functions:** The `calculate_total()` function.
- **Classes and objects:** The `Product` class and its instances.

This demonstrates how fundamental programming concepts work together to create a structured application.

---

## 6. Key Takeaways

| Concept     | Purpose                                                                      |
| ----------- | ---------------------------------------------------------------------------- |
| Identifiers | Give meaningful names to programming elements                                |
| Variables   | Reference values that can change                                             |
| Constants   | Represent values intended to remain fixed                                    |
| Arrays      | Store ordered collections with fixed capacity in traditional implementations |
| Vectors     | Provide dynamically resizable collections                                    |
| Functions   | Organize reusable operations                                                 |
| Classes     | Define blueprints for objects                                                |
| Objects     | Combine data and behavior                                                    |

The central lesson is that programming is not only about writing instructions. It is also about organizing data, dividing responsibilities, and structuring code to support maintainability and future development.

Understanding these concepts provides an important foundation for learning Python, Django, and Django REST Framework.

---

## 7. What I Learned

Through this lesson, I developed a better understanding of how programming languages organize information and behavior.

I learned that identifiers make code easier to understand, containers help manage collections of data, functions reduce duplication, and OOP provides a structured way to represent entities and their interactions.

These concepts are particularly important for backend development because backend applications frequently process data, execute business logic, interact with databases, and expose functionality through APIs.

As I continue progressing through the IBM Back-End Development Professional Certificate, I will build on these fundamentals to understand how real-world applications are designed and implemented.

---

**Learning Resources:** IBM Back-End Development Professional Certificate — Introduction to Software Engineering.

_This article documents my learning journey and is intended for educational purposes._
