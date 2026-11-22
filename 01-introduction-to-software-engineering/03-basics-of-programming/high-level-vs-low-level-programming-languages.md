# High-Level vs. Low-Level Programming Languages: Understanding Query and Assembly Languages

## Introduction

Programming languages allow humans to communicate instructions to computers. However, not all programming languages communicate with computers in the same way or at the same level of abstraction.

Some languages are designed to make programming easier by hiding complicated hardware details. Others provide more direct control over computer hardware, memory, and processor instructions.

This brings us to two important classifications:

- **High-level programming languages:** Languages that provide abstractions and human-readable syntax, allowing developers to focus on application logic.
- **Low-level programming languages:** Languages that are closer to the computer's hardware and expose more details about how instructions are executed.

While learning about programming languages, I also explored two interesting categories: **query languages**, particularly SQL, and **assembly languages**, which provide a symbolic representation of machine instructions.

Understanding these concepts helps explain how the different layers of software development work together, especially in backend development.

---

## 1. Understanding Programming Language Abstraction

Before comparing high-level and low-level languages, it is important to understand the concept of abstraction.

**Abstraction** means hiding unnecessary implementation details and exposing only the information or functionality needed to perform a particular task.

For example, imagine driving a car.

You use the steering wheel, accelerator, and brake pedals without needing to understand every mechanical operation happening inside the engine.

Programming languages work similarly.

When writing Python, developers can perform complex operations without manually controlling CPU registers or managing every memory operation.

The language and its underlying runtime or execution environment handle many of these details.

The level of abstraction determines how much of the underlying computer implementation a developer needs to understand and control.

## 2. High-Level Programming Languages

A high-level programming language is designed to make programming easier for humans.

It provides readable syntax, meaningful keywords, and abstractions that hide many hardware-specific details.

For example, consider this Python code:

```python
price = 100
quantity = 3

total = price * quantity

print(total)
```

The code is relatively easy to understand. We can recognize that it multiplies the product price by its quantity and displays the result.

We do not need to specify:

- Which CPU register should store the price.
- Which memory address should contain the quantity.
- Which processor instruction should perform multiplication.
- How the result should be stored at the hardware level.

These implementation details are handled by the language implementation and execution environment.

### 2.1 Characteristics of High-Level Languages

**1. Human-readable syntax**

High-level languages use syntax and structures designed to be understandable by developers.

For example, Python uses:

```python
if age >= 18:
    print("Adult")
```

This is easier to understand than manually writing the corresponding processor instructions.

**2. Hardware abstraction**

Developers generally do not need to interact directly with CPU registers or physical memory addresses.

**3. Easier development and maintenance**

Readable syntax and reusable abstractions make it easier to build, debug, test, and maintain applications.

**4. Portability**

Many high-level languages can run on different operating systems and processor architectures, provided the appropriate interpreter, compiler, or runtime is available.

### 2.2 Examples of High-Level Languages

- Python
- Java
- JavaScript
- C#
- Pascal
- SQL (a high-level, domain-specific query language)

High-level languages are commonly used in web development, backend systems, mobile applications, data processing, and many other areas.

### 2.3 Why Are High-Level Languages Important in Backend Development?

Imagine developing an e-commerce backend using Django.

You need to calculate product prices, authenticate customers, process orders, and communicate with a database.

Python allows you to focus on these application requirements instead of manually managing processor instructions.

For example:

```python
def calculate_order_total(price, quantity):
    return price * quantity
```

This small function represents business logic without exposing the underlying hardware operations.

That is one of the biggest advantages of high-level programming languages: they allow developers to focus on solving problems at the application level.

---

## 3. Low-Level Programming Languages

Low-level programming languages are closer to the computer's hardware.

Unlike high-level languages, they expose more details about how a processor executes instructions and interacts with memory.

Assembly language is one of the most common examples.

Low-level languages generally provide less abstraction, meaning developers need a better understanding of the underlying hardware architecture.

### 3.1 Characteristics of Low-Level Languages

**1. Hardware dependency**

Low-level languages are often designed for particular processor architectures.

For example, x86 assembly instructions are different from ARM assembly instructions.

Code written for one architecture cannot necessarily execute directly on another.

**2. Greater hardware control**

Developers can work with processor registers, memory addresses, and specific machine instructions.

**3. Less abstraction**

The programmer has more responsibility for understanding how operations are performed at the hardware level.

**4. More complex development**

Writing and maintaining low-level code can be more difficult because developers work closer to the processor's actual operations.

### 3.2 Examples of Low-Level Languages

Assembly languages associated with processor architectures include:

- x86 Assembly
- ARM Assembly
- MIPS Assembly

Machine code, which consists of binary instructions executed by the processor, is at an even lower level.

---

## 4. Query Languages

A query language is a language designed to request, retrieve, or manipulate information from a data source.

In backend development, query languages are especially important because applications frequently need to communicate with databases.

The most widely used database query language is SQL (Structured Query Language).

SQL allows developers to interact with relational databases without manually specifying how the database should locate and retrieve information at the hardware level.

### 4.1 Understanding SQL

Imagine an e-commerce application with a database table called `products`.

It contains information such as:

| id  | name     | price |
| --- | -------- | ----- |
| 1   | Laptop   | 1200  |
| 2   | Keyboard | 80    |
| 3   | Mouse    | 30    |

We can use SQL to interact with this table.

### 4.2 Retrieving Data: SELECT

The `SELECT` statement retrieves information from a database.

```sql
SELECT * FROM products;
```

This retrieves all columns and records from the `products` table.

We can also retrieve specific columns:

```sql
SELECT name, price
FROM products;
```

Or retrieve products with a particular condition:

```sql
SELECT *
FROM products
WHERE price < 100;
```

This returns products whose prices are below 100.

### 4.3 Modifying Data

SQL also provides statements for modifying database records.

**INSERT: Adding records**

```sql
INSERT INTO products (name, price)
VALUES ('Monitor', 250);
```

This adds a new product to the table.

**UPDATE: Modifying records**

```sql
UPDATE products
SET price = 220
WHERE name = 'Monitor';
```

This changes the price of the specified product.

**DELETE: Removing records**

```sql
DELETE FROM products
WHERE name = 'Monitor';
```

This removes the matching product.

An important point when using `UPDATE` and `DELETE` is the `WHERE` clause. Without an appropriate condition, these statements can affect every record in the table.

### 4.4 Understanding CRUD Operations

CRUD is an acronym describing the four fundamental operations performed on persistent data:

| CRUD operation | SQL statement | Meaning                 |
| -------------- | ------------- | ----------------------- |
| Create         | INSERT        | Add new records         |
| Read           | SELECT        | Retrieve records        |
| Update         | UPDATE        | Modify existing records |
| Delete         | DELETE        | Remove records          |

CRUD is not exclusive to SQL. It is a general concept used across many applications and data-management systems.

For example, in an e-commerce application:

- Create: A customer adds a new shipping address.
- Read: The application retrieves the customer's orders.
- Update: A customer changes their profile information.
- Delete: A customer removes a saved address.

### 4.5 Is SQL a Programming Language?

SQL is generally classified as a high-level, domain-specific language.

Unlike general-purpose languages such as Python, which can be used to build many different types of applications, SQL focuses primarily on working with data.

Another important distinction is that SQL is primarily **declarative**.

This means developers describe what they want the database to do rather than specifying every step required to achieve it.

For example:

```sql
SELECT *
FROM products
WHERE price < 100;
```

We describe the data we want. The database management system determines how to execute the query, potentially using indexes and query optimization techniques.

This is different from an imperative approach, where the programmer explicitly describes the sequence of operations.

---

## 5. Assembly Languages

Assembly language is a low-level programming language that provides a human-readable representation of machine instructions.

Computers execute machine code, which consists of binary instructions understood by a processor.

Writing programs directly in binary would be extremely difficult for humans.

Assembly languages solve this problem by replacing binary instruction patterns with symbolic names called **mnemonics**.

### 5.1 Understanding Assembly Instructions

Consider this simplified x86 assembly example:

```asm
MOV AX, 5
ADD AX, 3
```

Let's understand the instructions.

- `MOV` is an instruction used to move or copy data.
- `AX` is a CPU register in x86 architecture.
- `5` is the value being placed in the register.
- `ADD` performs an addition operation.
- `3` is added to the value currently stored in `AX`.

After these instructions execute, the register contains the value `8`.

A register is a small, high-speed storage location inside the CPU that holds data needed during instruction execution.

Assembly instructions allow programmers to work directly with these processor-level concepts.

### 5.2 What Is an Assembler?

An assembler is a program that translates assembly language into machine code.

The general process looks like this:

1. A developer writes assembly instructions.
2. The assembler translates those instructions into machine-code instructions.
3. The resulting object code can be linked with other object files and libraries.
4. The resulting executable can be loaded and executed by the operating system and processor.

### 5.3 Assembly Language and Machine Code

Assembly language and machine code are closely related, but they are not the same thing.

| Assembly language                   | Machine code                                      |
| ----------------------------------- | ------------------------------------------------- |
| Uses symbolic instructions          | Uses binary instruction encodings                 |
| Human-readable compared with binary | Designed for processor execution                  |
| Written by programmers              | Produced by assemblers or other translation tools |
| Architecture-specific               | Architecture-specific                             |

For example, an assembly instruction such as `MOV` has a corresponding machine-code encoding determined by the processor architecture and instruction operands.

### 5.4 Does Every Assembly Instruction Correspond to One Machine Instruction?

In traditional assembly, an instruction generally represents one machine instruction.

However, there are exceptions.

Some assemblers support pseudo-instructions or macros that expand into multiple machine instructions.

Therefore, it is more accurate to say that ordinary assembly instructions usually map closely to machine instructions, while certain assembler-specific constructs can expand into several instructions.

---

## 6. How High-Level and Low-Level Languages Work Together

One important thing I learned is that high-level and low-level languages are not competing technologies.

They operate at different abstraction levels and often work together.

Consider a Python application.

When Python code executes, the Python implementation handles the process of translating and executing the program's operations.

For example, in the standard CPython implementation:

1. Python source code is compiled into Python bytecode.
2. The Python virtual machine executes that bytecode.
3. CPython and its underlying runtime rely on native machine instructions to perform the actual operations.

This illustrates how developers can write high-level code while lower-level operations happen behind the scenes.

The exact execution process depends on the language implementation.

---

## 7. Connecting Everything to Backend Development: Python, Django, SQL, and the Database

Let's bring all these concepts together through a practical e-commerce backend scenario.

Imagine a customer opens an online store and requests products priced below 100.

The backend might contain this Django ORM query:

```python
products = Product.objects.filter(price__lt=100)
```

What happens behind the scenes?

**Step 1: Python**

The developer writes Python code to describe the application's behavior.

**Step 2: Django ORM**

Django ORM provides a high-level interface for interacting with database records.

It translates the ORM operation into an appropriate SQL query.

**Step 3: SQL**

The database receives a query conceptually similar to:

```sql
SELECT *
FROM products
WHERE price < 100;
```

**Step 4: Database Management System**

The database management system parses, plans, and executes the SQL query.

It determines how to retrieve the requested records, potentially using indexes and other optimization techniques.

**Step 5: Hardware execution**

The database software ultimately relies on the operating system, processor, memory, and storage devices to perform the required operations.

The processor executes machine instructions as part of this process.

The simplified relationship looks like this:

```text
Backend Developer
       |
       v
Python Application
       |
       v
Django ORM
       |
       v
SQL Query
       |
       v
Database Management System
       |
       v
Operating System and Hardware
       |
       v
Processor executes machine instructions
```

This example demonstrates how different technologies work together to make a backend application function.

It also explains why understanding SQL remains important even when using an ORM: the ORM simplifies database interaction, but it does not eliminate the underlying database concepts.

---

## 8. Key Differences: High-Level vs. Low-Level Languages

| Comparison             | High-Level Languages | Low-Level Languages     |
| ---------------------- | -------------------- | ----------------------- |
| Abstraction            | Higher               | Lower                   |
| Readability            | Generally easier     | Generally harder        |
| Hardware dependency    | Generally less       | Generally more          |
| Hardware control       | More indirect        | More direct             |
| Development complexity | Generally lower      | Generally higher        |
| Portability            | Often higher         | Often lower             |
| Examples               | Python, Java, C#     | x86, ARM, MIPS Assembly |

These are general characteristics rather than absolute rules. Some languages, such as C, occupy a middle ground because they provide both high-level language features and relatively direct access to memory.

---

## 9. Key Takeaways

After exploring this topic, these are the main concepts I want to remember:

1. High-level languages provide abstractions that make programming easier and more readable.
2. Low-level languages operate closer to computer hardware and expose more implementation details.
3. SQL is a high-level, declarative query language designed primarily for interacting with databases.
4. CRUD represents Create, Read, Update, and Delete, the four fundamental data operations.
5. Assembly language uses symbolic instructions called mnemonics to represent processor operations.
6. An assembler translates assembly language into machine code.
7. Assembly instructions are architecture-dependent.
8. High-level applications ultimately rely on lower-level software and hardware operations.
9. Django ORM demonstrates how high-level abstractions simplify database interactions while SQL remains important underneath.

## Conclusion

Learning about high-level and low-level programming languages helped me understand that programming does not happen at just one level.

As backend developers, we usually work with high-level languages such as Python and frameworks such as Django. However, our applications depend on several underlying layers, including SQL, database management systems, operating systems, and processor instructions.

Understanding how these layers relate to one another gives us a better picture of what happens behind the code we write.

This is another step in my journey through the IBM Back-End Development Professional Certificate, and it reinforces an important lesson: understanding the foundations behind the tools we use makes us better developers.
