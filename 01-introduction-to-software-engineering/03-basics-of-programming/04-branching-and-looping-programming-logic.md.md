# Branching and Looping Programming Logic

## 1. Introduction

A computer program is more than a collection of instructions executed one after another. Real-world applications need to make decisions, respond to different situations, and repeat certain operations when necessary.

Consider an e-commerce application.

When a customer places an order, the system needs to:

- Check whether the customer has enough balance or whether the payment was successful.
- Determine whether a product is available in stock.
- Decide whether an order should be confirmed or rejected.
- Process multiple products in an order.
- Repeat certain operations until all items have been processed.

How does a program handle these situations?

Two fundamental programming logic concepts make this possible:

**Branching:** Allows a program to make decisions and choose between different execution paths.

**Looping:** Allows a program to repeat a block of instructions multiple times based on a condition or a defined number of iterations.

Together, branching and looping provide the foundation for controlling the flow of a program.

---

## 2. Understanding Programming Logic

Programming logic describes how instructions are organized and executed to solve a particular problem.

When writing a program, we need to control three fundamental aspects of execution:

1. **Sequence:** Instructions execute one after another in a specific order.
2. **Selection (Branching):** The program chooses which instructions to execute based on conditions.
3. **Iteration (Looping):** The program repeats instructions while a particular condition remains satisfied or for a defined number of iterations.

For example, imagine processing an online order:

- Sequence: Receive the order and retrieve its information.
- Selection: Check whether the payment was successful.
- Iteration: Go through every product in the order and update its inventory.

These three concepts are commonly known as the fundamental control structures of structured programming.

---

## 3. Boolean Expressions and Variables

Before understanding branching and looping, we need to understand two important building blocks: Boolean expressions and variables.

### 3.1 What Are Boolean Expressions?

A Boolean expression is an expression that evaluates to one of only two possible values:

- `True`
- `False`

Boolean expressions are essential because programs use them to make decisions.

For example, consider an e-commerce application that needs to check whether a product is available.

```python
stock_quantity = 10

is_available = stock_quantity > 0

print(is_available)  # True
```

The expression `stock_quantity > 0` compares the stock quantity with zero.

Because the quantity is 10, the expression evaluates to `True`.

If the stock quantity were zero, the result would be `False`.

### Comparison Operators

Python provides several comparison operators for creating Boolean expressions:

| Operator | Meaning | Example |
|---|---|---|
| `==` | Equal to | `price == 100` |
| `!=` | Not equal to | `status != "cancelled"` |
| `>` | Greater than | `stock > 0` |
| `<` | Less than | `age < 18` |
| `>=` | Greater than or equal to | `quantity >= 5` |
| `<=` | Less than or equal to | `price <= 500` |

These operators allow programs to compare values and determine whether specific conditions are satisfied.

### Logical Operators

Sometimes a decision depends on more than one condition.

Python provides three main logical operators:

- `and`: Returns `True` when both conditions are true.
- `or`: Returns `True` when at least one condition is true.
- `not`: Reverses a Boolean value.

Example:

```python
stock_quantity = 10
product_is_active = True

can_purchase = (
    stock_quantity > 0
    and product_is_active
)

print(can_purchase)  # True
```

The product can be purchased only when it has available stock and is active.

If either condition is false, the entire expression evaluates to false.

### 3.2 What Are Variables?

A variable is a named reference used to access a value during program execution.

Variables allow programs to store and work with information that may change.

For example:

```python
customer_name = "Mostafa"
order_total = 250
payment_status = "pending"
```

Here, we have three variables representing different pieces of information.

A variable's value can change:

```python
order_total = 250

order_total = order_total + 50

print(order_total)  # 300
```

Variables are important in branching and looping because conditions frequently depend on their values.

For example:

```python
stock_quantity = 5

while stock_quantity > 0:
    print("Product available")
    stock_quantity -= 1
```

The variable `stock_quantity` changes during execution, eventually making the loop condition false.

### Variables and Functions

Variables can also be passed to functions as arguments.

```python
def calculate_discount(price, discount_percentage):
    discount = price * discount_percentage / 100
    return price - discount


final_price = calculate_discount(200, 10)

print(final_price)  # 180.0
```

The function receives values through its parameters and uses them to perform calculations.

This is particularly important in backend development, where functions receive information from users, databases, APIs, and other application components.

---

## 4. Branching Logic (Decision-Making)

Branching is a programming concept that allows a program to choose between different execution paths depending on whether certain conditions are true or false.

Without branching, a program would execute instructions sequentially without adapting its behavior to different situations.

Imagine an online store:

- If a customer successfully pays, confirm the order.
- Otherwise, keep the order pending or reject it.

The application needs to evaluate the payment status before deciding what happens next.

This is exactly what branching provides.

### 4.1 The `if` Statement

The `if` statement executes a block of code only when its condition evaluates to `True`.

Syntax:

```python
if condition:
    # Execute this block if condition is True
```

Example:

```python
stock_quantity = 10

if stock_quantity > 0:
    print("Product is available")
```

Because the stock quantity is greater than zero, the condition evaluates to true, and the message is displayed.

If the condition is false, the code inside the `if` block is skipped.

### 4.2 The `if-else` Statement

Sometimes a program needs to handle both possible outcomes.

The `if-else` statement provides two execution paths:

- One when the condition is true.
- Another when the condition is false.

Example:

```python
stock_quantity = 0

if stock_quantity > 0:
    print("Product is available")
else:
    print("Product is out of stock")
```

Since the stock quantity is zero, the program executes the `else` block.

This is useful whenever an application must choose between two alternatives.

### 4.3 The `if-elif-else` Statement

Real-world applications frequently require more than two possible outcomes.

Python provides `elif` (short for else if) to evaluate multiple conditions.

Example:

```python
order_total = 250

if order_total >= 500:
    discount = 20
elif order_total >= 200:
    discount = 10
elif order_total >= 100:
    discount = 5
else:
    discount = 0

print(f"Discount: {discount}%")
```

The program evaluates the conditions from top to bottom.

Once it finds a condition that evaluates to true, it executes that block and skips the remaining branches.

The order of conditions matters. If a broader condition is placed before a narrower one, it might prevent the narrower condition from ever being reached.

### 4.4 Nested Conditions

A nested condition is an `if` statement placed inside another conditional block.

It is useful when one decision depends on the outcome of another decision.

Example:

```python
payment_successful = True
stock_quantity = 5

if payment_successful:
    if stock_quantity > 0:
        print("Order confirmed")
    else:
        print("Product unavailable")
else:
    print("Payment failed")
```

The program first checks the payment status.

Only if payment succeeds does it check the product's availability.

Nested conditions can represent complex decision-making, although excessive nesting can make code harder to read. In larger applications, combining conditions or extracting logic into functions can improve readability.

### 4.5 The `switch` Statement and Its Equivalent in Python

Some programming languages provide a `switch` statement.

A switch statement compares an expression against multiple possible values and executes the matching branch.

For example, an application might use an order status:

```text
switch (order_status):
    case "pending":
        process_pending_order()
    case "paid":
        confirm_order()
    case "cancelled":
        cancel_order()
```

Python does not use the traditional `switch` keyword. Instead, Python 3.10 and later provide `match-case`.

Example:

```python
order_status = "paid"

match order_status:
    case "pending":
        print("Order is waiting for payment")

    case "paid":
        print("Order is confirmed")

    case "cancelled":
        print("Order has been cancelled")

    case _:
        print("Unknown order status")
```

The `_` pattern acts as a default case.

**Important distinction:** `match-case` supports structural pattern matching, which is more powerful than a traditional switch statement.

### 4.6 What About `goto`?

`goto` is a branching statement available in some programming languages.

It transfers program execution directly to a labeled instruction elsewhere in the code.

However, unrestricted use of `goto` can make program flow difficult to understand and maintain because execution can jump between different locations unexpectedly.

This can create what is commonly called spaghetti code.

Structured programming generally favors `if`, `else`, loops, functions, and other structured control mechanisms instead.

---

## 5. Looping Logic (Repetition)

Branching allows programs to make decisions. Looping allows programs to repeat operations.

Imagine an order containing 100 products.

We could write 100 separate instructions to process every product, but that would be inefficient and difficult to maintain.

Instead, we can use a loop to execute the same logic for every item.

A loop repeatedly executes a block of instructions according to a particular condition or iteration rule.

### 5.1 The `while` Loop

A `while` loop repeatedly executes a block of code as long as its condition evaluates to `True`.

Syntax:

```python
while condition:
    # Instructions to repeat
```

Example:

```python
stock_quantity = 3

while stock_quantity > 0:
    print("Selling one product")

    stock_quantity -= 1

print("Product is out of stock")
```

Execution:

1. The program checks whether stock is greater than zero.
2. If true, it executes the loop body.
3. It decreases the stock quantity by one.
4. It checks the condition again.
5. When stock reaches zero, the condition becomes false and the loop stops.

The loop executes three times.

**Important:** Always make sure that a condition in a `while` loop can eventually become false when termination is intended.

Otherwise, the program may enter an infinite loop.

### 5.2 The `for` Loop

A `for` loop is used to iterate over a sequence or iterable, such as a list, tuple, string, or range of numbers.

Example:

```python
products = ["Laptop", "Phone", "Keyboard"]

for product in products:
    print(f"Processing {product}")
```

Output:

```text
Processing Laptop
Processing Phone
Processing Keyboard
```

The loop automatically retrieves each item from the list and executes the loop body.

Another common use is the `range()` function.

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

`range(5)` generates numbers starting from zero up to, but not including, five.

The `for` loop is particularly useful when processing collections of data.

### 5.3 The `do-while` Loop

A `do-while` loop is similar to a `while` loop, but there is an important difference:

- A `while` loop checks its condition before executing the body.
- A `do-while` loop executes its body first and checks the condition afterward.

This means a `do-while` loop always executes at least once.

Conceptual example:

```text
do:
    display_menu()
    get_user_choice()

while user_choice != "exit"
```

This is useful when an operation must happen at least once, such as displaying a menu before asking the user whether they want to continue.

Python does not have a native `do-while` statement.

However, we can achieve similar behavior using `while True` and `break`:

```python
while True:
    choice = input("Enter a command: ")

    if choice == "exit":
        break

    print(f"You selected: {choice}")
```

Here:

- `while True` starts a loop that would otherwise continue indefinitely.
- `break` immediately terminates the loop when the exit condition is satisfied.

---

## 6. Controlling Loop Execution

In addition to loop conditions, programming languages provide statements that control how loops execute.

Two particularly important statements are `break` and `continue`.

### 6.1 The `break` Statement

`break` immediately terminates the nearest enclosing loop.

Example:

```python
products = ["Laptop", "Phone", "Keyboard"]

for product in products:
    if product == "Phone":
        break

    print(product)
```

Output:

```text
Laptop
```

When the program encounters `"Phone"`, the condition becomes true, and `break` terminates the loop.

The remaining products are not processed.

### 6.2 The `continue` Statement

`continue` skips the remaining instructions in the current iteration and moves to the next iteration.

Example:

```python
products = ["Laptop", "Phone", "Keyboard"]

for product in products:
    if product == "Phone":
        continue

    print(product)
```

Output:

```text
Laptop
Keyboard
```

Unlike `break`, `continue` does not terminate the entire loop.

It only skips the current iteration.

### Understanding the Difference

| Statement | Behavior |
|---|---|
| `break` | Terminates the loop completely |
| `continue` | Skips the current iteration |
| Normal execution | Continues with the next instruction |

Understanding this distinction is important when processing collections, filtering data, or handling exceptional conditions.

---

## 7. Branching and Looping Working Together

Branching and looping are often used together to solve practical problems.

Consider an e-commerce application that processes a collection of orders.

For every order, the system checks whether the payment was successful.

```python
orders = [
    {"id": 1, "payment_status": "paid"},
    {"id": 2, "payment_status": "pending"},
    {"id": 3, "payment_status": "paid"},
    {"id": 4, "payment_status": "failed"},
]

for order in orders:

    if order["payment_status"] == "paid":
        print(f"Order {order['id']} confirmed")

    elif order["payment_status"] == "pending":
        print(f"Order {order['id']} awaiting payment")

    else:
        print(f"Order {order['id']} cannot be confirmed")
```

Here is what happens:

1. The `for` loop iterates through every order.
2. The `if` statement checks its payment status.
3. The appropriate branch executes.
4. The loop moves to the next order.
5. The process continues until all orders have been processed.

This example demonstrates how looping handles repetition while branching handles decisions.

Together, they allow applications to process large amounts of data while responding appropriately to different conditions.

---

## 8. Branching and Looping in Backend Development

These concepts are not limited to beginner programming exercises. They are essential parts of real backend applications.

Consider a Django e-commerce backend.

### Branching in Django

A Django view might check whether a product exists before returning its information.

```python
from django.http import JsonResponse
from .models import Product

def product_detail(request, product_id):

    try:
        product = Product.objects.get(id=product_id)

    except Product.DoesNotExist:
        return JsonResponse(
            {"error": "Product not found"},
            status=404
        )

    if product.stock_quantity > 0:
        availability = "Available"
    else:
        availability = "Out of stock"

    return JsonResponse({
        "name": product.name,
        "availability": availability
    })
```

This example demonstrates how conditional logic helps a backend respond differently depending on database information.

### Looping in Django

Suppose we need to process a collection of products.

```python
products = Product.objects.all()

for product in products:
    print(product.name)
```

The loop iterates over the products returned by the database query.

In real Django applications, however, we should also consider query efficiency and use appropriate ORM operations rather than unnecessarily loading and processing large collections in Python.

### Branching and Looping in Django REST Framework

In Django REST Framework, serializers frequently use validation logic to determine whether incoming data is acceptable.

For example:

```python
from rest_framework import serializers

class ProductSerializer(serializers.Serializer):
    name = serializers.CharField(max_length=100)
    price = serializers.DecimalField(
        max_digits=10,
        decimal_places=2
    )
    stock_quantity = serializers.IntegerField()

    def validate_price(self, value):
        if value <= 0:
            raise serializers.ValidationError(
                "Price must be greater than zero."
            )

        return value
```

The `if` statement checks a business rule.

If the condition is true, the serializer raises a validation error. Otherwise, it returns the validated value.

This illustrates how branching supports business rules and data validation in backend applications.

---

## 9. Common Mistakes and Best Practices

Understanding control structures also means knowing how to use them correctly.

### Mistake 1: Forgetting to Update a While Loop Condition

```python
counter = 0

while counter < 5:
    print(counter)
```

This creates an infinite loop because `counter` never changes.

Correct version:

```python
counter = 0

while counter < 5:
    print(counter)
    counter += 1
```

### Mistake 2: Incorrect Condition Ordering

When using `if-elif-else`, conditions are evaluated from top to bottom.

Putting a broad condition first may prevent more specific conditions from being executed.

Always consider the logical order of your conditions.

### Mistake 3: Using Loops When They Are Not Necessary

Sometimes a direct operation or a built-in function is clearer and more efficient than writing a loop manually.

For example, Python provides `sum()` to calculate the total of numeric values:

```python
prices = [100, 200, 300]

total = sum(prices)
```

### Best Practices

- Write clear and meaningful conditions.
- Avoid unnecessarily complicated nested conditions.
- Ensure loops have a clear termination strategy.
- Use `for` loops when iterating over collections.
- Use `while` loops when repetition depends on a changing condition.
- Avoid unnecessary use of `break` and `continue` when they make execution difficult to understand.
- Keep branching and looping logic focused and readable.

---

## 10. Key Takeaways

Branching and looping are fundamental control structures that determine how a program executes its instructions.

**Branching:**
- Enables decision-making.
- Uses Boolean expressions to evaluate conditions.
- Includes `if`, `if-else`, `if-elif-else`, and language-specific constructs such as `switch` or Python's `match-case`.

**Looping:**
- Enables repeated execution.
- Includes `for` and `while` loops in Python.
- Allows programs to process collections and repeat operations.
- Can be controlled using statements such as `break` and `continue`.

**The most important distinction:**

Branching determines *which instructions should execute*, while looping determines *how many times instructions should execute*.

In practical software development, these concepts work together to create applications that can make decisions, process information, and respond to different situations.

They are also essential foundations for understanding more advanced topics in Python, Django, and Django REST Framework.

---

## What I Learned

While studying branching and looping, I learned that programming is not simply about writing instructions in sequence.

A program also needs to make decisions based on conditions and repeat operations when necessary.

Understanding Boolean expressions helped me see how programs evaluate conditions, while branching and looping showed me how those conditions control execution.

These concepts are especially important in backend development because applications constantly validate data, enforce business rules, process collections, and handle different scenarios.

This is another important step in building my understanding of programming logic as part of my IBM Back-End Development Professional Certificate journey.