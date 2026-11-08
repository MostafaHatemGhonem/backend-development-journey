# Understanding Software Testing: Types and Levels

## Overview

Software testing helps verify that an application meets its requirements, behaves correctly, and maintains its quality when changes are introduced.

In the previous topic, [Building Quality Software](./building-quality-software.md), we introduced testing as an essential activity in software quality.

This document explores two important ways to classify software testing:

1. **Testing Types:** What aspect of the software are we testing?
2. **Testing Levels:** What scope of the software are we testing?

---

## 1. Types of Software Testing

### 1.1 Functional Testing

Functional testing verifies that software features behave according to specified functional requirements.

It checks inputs, expected outputs, and application behavior.

**Example: E-commerce login**

- Input: Valid email and password.
- Expected output: Successful authentication.
- Input: Invalid credentials.
- Expected output: An appropriate error response.

Functional testing commonly uses black-box testing techniques, where the internal implementation is not the primary focus.

### 1.2 Non-Functional Testing

Non-functional testing evaluates software quality attributes rather than individual business features.

Important areas include:

| Attribute    | Description                                                           |
| ------------ | --------------------------------------------------------------------- |
| Performance  | Measures response time and system efficiency.                         |
| Security     | Evaluates protection against unauthorized access and vulnerabilities. |
| Scalability  | Checks the system's ability to handle increased workloads.            |
| Availability | Measures whether the application remains accessible when needed.      |

**Example:** Testing whether an e-commerce backend can handle thousands of simultaneous users during a major sale.

### 1.3 Regression Testing

Regression testing verifies that existing functionality continues working after code changes, bug fixes, or updates.

**Example:** After adding a new payment method, developers rerun existing payment tests to ensure the original payment functionality has not broken.

Regression testing can be performed at multiple testing levels.

---

## 2. Levels of Software Testing

Testing levels describe the scope of testing within an application.

### 2.1 Unit Testing

Tests individual units of code, such as functions, methods, or classes.

**Example:** Testing a function that calculates an order's total price.

**Purpose:** Detect errors early and verify individual components independently.

### 2.2 Integration Testing

Tests interactions and communication between multiple components or modules.

**Example:** Verifying that the order, payment, and inventory modules communicate correctly when a customer places an order.

**Purpose:** Identify problems that occur when components work together.

### 2.3 System Testing

Tests the complete integrated application against its specified requirements.

**Example:** Testing an entire e-commerce purchasing workflow, from customer login to successful order creation.

**Purpose:** Verify that the complete application behaves as expected.

### 2.4 Acceptance Testing

Verifies whether the application satisfies user needs and business requirements.

**Example:** A customer or business stakeholder tests the e-commerce application before accepting the final product.

Common forms include:

- User Acceptance Testing (UAT).
- Business Acceptance Testing.
- Operational Acceptance Testing.

**Purpose:** Confirm that the software is ready for its intended use.

---

## 3. Testing Types vs. Testing Levels

These classifications describe different dimensions of software testing.

| Testing Types  | Testing Levels |
| -------------- | -------------- |
| Functional     | Unit           |
| Non-Functional | Integration    |
| Regression     | System         |
|                | Acceptance     |

**Testing types** describe what aspect of the software is being evaluated.

**Testing levels** describe the scope at which testing is performed.

They can overlap. For example, regression testing can be performed at unit, integration, or system level.

---

## 4. Key Takeaways

- Functional testing verifies whether features meet functional requirements.
- Non-functional testing evaluates quality attributes such as performance, security, and scalability.
- Regression testing ensures that changes do not break existing functionality.
- Unit testing focuses on individual code components.
- Integration testing checks communication between components.
- System testing evaluates the complete application.
- Acceptance testing confirms that the software meets user and business expectations.

**Main takeaway:** Testing types and testing levels complement each other. Together, they provide different perspectives for evaluating software quality and reliability.

---

## Related Learning Materials

- [Building Quality Software: What Makes Software Truly Good?](https://mostafa-hatem-backend.hashnode.dev/building-quality-software-what-makes-software-truly-good)

_Part of my learning journey through the IBM Back-End Development Professional Certificate._
