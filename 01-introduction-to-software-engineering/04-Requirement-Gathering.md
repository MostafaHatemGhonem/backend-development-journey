# Requirement Gathering Process and Requirement Specification Documents

## Introduction

Before developing any software application, developers need to understand what they are building, why they are building it, and what users expect from it.

This is where **Requirement Gathering** comes into the Software Development Life Cycle (SDLC).

Requirement gathering is the process of identifying, collecting, analyzing, and documenting the needs and expectations of stakeholders before software development begins.

It helps the development team understand the actual problem they are solving instead of making assumptions about what the client wants.

For example, imagine a company wants to build an e-commerce application. Before writing Python code, creating Django models, or designing REST APIs, the team needs to understand:

- Who will use the application?
- What features should it provide?
- What problems should it solve?
- What performance and security expectations must it satisfy?
- Which features should be developed first?

These questions are addressed during requirements engineering.

---

## 1. Requirement Gathering Process

The requirement gathering process consists of six main steps.

### 1.1 Identify Stakeholders

A stakeholder is any individual, group, or organization that has an interest in the software or is affected by its development and operation.

Identifying stakeholders helps the development team understand whose needs and expectations must be considered.

**Examples of stakeholders in an e-commerce application:**

- Customers: Purchase products and track orders.
- Administrators: Manage users, products, and orders.
- Store owners: Monitor sales and manage inventory.
- Business managers: Define business goals.
- Developers: Implement and maintain the application.
- System administrators: Manage infrastructure and deployment.

Each stakeholder may have different expectations and priorities.

### 1.2 Establish Goals and Objectives

After identifying stakeholders, the team needs to understand what the organization wants to achieve.

Although goals and objectives are related, they have different meanings.

**Goals:**

- Broad outcomes the organization wants to achieve.
- Describe the overall direction or desired result.

**Objectives:**

- Specific actions or measurable results.
- Explain how the organization plans to achieve its goals.

**Example:**

- Goal: Improve the online shopping experience.
- Objective: Allow customers to search for products, add them to a cart, and complete purchases through a simple checkout process.

The distinction is important because broad goals need to be translated into clear, actionable objectives.

### 1.3 Elicit Requirements

Requirement elicitation is the process of collecting information about stakeholder needs and expectations.

Common techniques include:

- **Interviews:** Discuss requirements directly with stakeholders.
- **Surveys:** Collect information from multiple users.
- **Workshops:** Bring stakeholders together to discuss requirements.
- **Observation:** Study how users currently perform their tasks.
- **Document analysis:** Review existing business documents and systems.

**Example:**

During interviews, customers explain that they need:

- Product search and filtering.
- Shopping cart functionality.
- Secure payment processing.
- Order tracking.

These become candidate requirements for the application.

### 1.4 Document Requirements

After collecting requirements, the team organizes and records them in requirement specification documents.

Documentation ensures that stakeholders, developers, testers, and project managers share a common understanding of what needs to be built.

For example, requirements might describe:

- User registration and authentication.
- Product management.
- Shopping cart operations.
- Order processing.
- Payment integration.

### 1.5 Confirm Requirements

Requirements must be reviewed with stakeholders to ensure that they accurately represent their needs.

This step helps identify:

- Missing requirements.
- Incorrect assumptions.
- Ambiguous descriptions.
- Conflicting expectations.
- Requirements that are difficult to understand or implement.

**Example:**

The development team documents that customers can reset forgotten passwords.

During review, the client confirms that password reset links must be sent through email and expire after a limited period.

This clarification prevents misunderstandings before implementation.

### 1.6 Prioritize Requirements

Not every requirement has the same importance.

The team must determine which requirements should receive attention first, considering business value, user needs, cost, risk, and available resources.

**Example:**

| Priority | Requirements                                      |
| -------- | ------------------------------------------------- |
| High     | Registration, login, product browsing, checkout   |
| Medium   | Product reviews, order history                    |
| Low      | Product recommendations, advanced personalization |

Prioritization helps the team focus on essential functionality before implementing less critical features.

---

## 2. Goals vs. Objectives

These concepts are commonly confused.

| Goals                            | Objectives                              |
| -------------------------------- | --------------------------------------- |
| Broad outcomes                   | Specific results                        |
| Describe what we want to achieve | Describe measurable actions or outcomes |
| Provide overall direction        | Help achieve the goals                  |
| Usually less detailed            | More specific and measurable            |

**Example:**

Goal: Increase customer satisfaction.

Objective: Reduce the average checkout process to fewer than five steps.

A good objective should be clear and measurable whenever possible.

---

## 3. Types of Requirement Specification Documents

After gathering and analyzing requirements, organizations document them using different types of requirement specifications.

Three important documents are:

1. Software Requirements Specification (SRS).
2. User Requirements Specification (URS).
3. System Requirements Specification (SysRS).

Each document has a different scope and purpose.

### 3.1 Software Requirements Specification (SRS)

SRS describes the requirements of the software application.

It explains what the software must do, how it should behave, and what quality expectations it must satisfy.

It acts as an important reference for developers, testers, project managers, and other technical stakeholders.

An SRS commonly includes:

**A. Functional Requirements**

Describe the specific operations and services the software must provide.

Examples:

- Users can register and log in.
- Customers can add products to their shopping carts.
- Customers can place orders.
- Administrators can create, update, and delete products.

**B. Non-Functional Requirements**

Describe quality attributes and constraints that determine how well the software operates.

Examples:

- API responses should complete within two seconds under a specified workload.
- User passwords must be securely stored.
- The application must support a specified number of concurrent users.
- The system should remain available according to its availability target.

**C. External Interface Requirements**

Describe how the software communicates or interacts with external systems, users, or other components.

Examples:

- Integration with an external payment gateway.
- Communication with an email service.
- REST API communication with a frontend application.

**D. System Features**

Describe major groups of related software functionality.

Examples:

- User authentication.
- Product management.
- Order management.
- Payment processing.

An SRS may also contain:

- Performance requirements.
- Design and implementation constraints.
- Assumptions.
- Dependencies.
- Data requirements.
- Security requirements.

The exact organization and section names can vary depending on the project and specification standard being followed.

### 3.2 User Requirements Specification (URS)

URS focuses on what users and business stakeholders need from the system.

It describes requirements from the user's perspective without necessarily explaining the technical implementation.

A common way to express user requirements is through **User Stories**.

A user story generally follows this structure:

> As a [type of user], I want [some functionality], so that [some benefit].

**Example:**

"As a customer, I want to add products to my shopping cart so that I can purchase multiple products together."

Breaking it down:

| Part                                              | Meaning                      |
| ------------------------------------------------- | ---------------------------- |
| As a customer                                     | Who needs the functionality? |
| I want to add products to my cart                 | What do they need?           |
| So that I can purchase multiple products together | Why do they need it?         |

URS may also contain use cases, business needs, user expectations, and acceptance criteria.

**Acceptance Criteria**

Acceptance criteria define the conditions that must be satisfied for a requirement or feature to be accepted.

For the shopping cart example:

- Customers can add available products to their carts.
- Customers can update product quantities.
- Customers can remove products from their carts.
- The cart displays the correct total price.

These conditions help guide acceptance testing.

### 3.3 System Requirements Specification (SysRS)

SysRS describes requirements for the complete system rather than only the software.

A system can consist of multiple components, including software, hardware, people, procedures, and operational environments.

For an e-commerce platform, SysRS may cover:

| Category            | Example                                             |
| ------------------- | --------------------------------------------------- |
| Software            | Django backend and frontend application             |
| Hardware            | Servers with sufficient processing power and memory |
| Security            | Access control and data protection                  |
| Performance         | Support for expected concurrent users               |
| Personnel           | System administrators and support staff             |
| Policies            | Business and operational procedures                 |
| Regulations         | Applicable data protection regulations              |
| Acceptance criteria | Conditions required before system approval          |

The important idea is that a complete system is more than a software application.

It includes everything needed to operate the solution successfully.

---

## 4. Comparing SRS, URS, and SysRS

These three documents describe requirements from different perspectives.

| Document | Main Focus                 | Main Question                       |
| -------- | -------------------------- | ----------------------------------- |
| URS      | User and business needs    | What do users need and why?         |
| SRS      | Software requirements      | What must the software do?          |
| SysRS    | Entire system requirements | What does the complete system need? |

Consider the following example:

**URS — User Need**

A customer wants to purchase products online.

**SRS — Software Requirements**

The application must provide product browsing, shopping cart, checkout, and payment functionality.

**SysRS — System Requirements**

The complete solution requires software, servers, security mechanisms, personnel, and operational procedures.

These documents are related, but they are not interchangeable.

Their development is also iterative; teams may refine them together as they discover more about the project.

---

## 5. Connecting Requirements to Backend Development

Understanding requirements is especially important for backend developers because they translate business and user needs into technical functionality.

Let's use the following user story:

"As a customer, I want to add products to my shopping cart so that I can purchase them later."

As a Django REST Framework developer, we can translate this requirement into possible technical components.

| Requirement                   | Possible Backend Implementation          |
| ----------------------------- | ---------------------------------------- |
| Store products                | Django Product model                     |
| Store customer carts          | Django Cart model                        |
| Store cart items              | Django CartItem model                    |
| Add products to cart          | DRF API endpoint                         |
| Update product quantities     | DRF update endpoint                      |
| Validate product availability | Serializer validation and business logic |
| Restrict cart access          | Authentication and permissions           |

A possible API endpoint:

```http
POST /api/cart/items/
```

Request body:

```json
{
  "product_id": 15,
  "quantity": 2
}
```

The backend should:

1. Validate the incoming request.
2. Check whether the product exists.
3. Check product availability.
4. Associate the cart item with the authenticated customer.
5. Save the item in the database.
6. Return an appropriate response.

The key lesson is that the user requirement describes the desired outcome, while the software requirement defines what the application must provide to achieve that outcome.

The technical implementation is then designed to satisfy those requirements.

---

## 6. Important Takeaways

- Requirement gathering helps developers understand what they are building before implementation begins.
- Stakeholders are the people or organizations affected by the software.
- Goals describe broad outcomes, while objectives describe more specific results.
- Requirement elicitation collects information through interviews, surveys, workshops, observation, and other techniques.
- Requirements must be documented, confirmed, and prioritized.
- URS focuses on user and business needs.
- SRS focuses on software functionality and quality requirements.
- SysRS covers the entire system, including software, hardware, personnel, and procedures.
- Backend developers translate requirements into database models, API endpoints, validation rules, permissions, and business logic.

## Conclusion

Requirement gathering is one of the foundations of successful software development.

A developer should not focus only on how to implement a feature. They must first understand why the feature is needed, who needs it, and what behavior is expected.

As I continue my IBM Back-End Development Professional Certificate learning journey, understanding these concepts helps me connect the software development process with the practical work of designing and building backend applications using Python, Django, and Django REST Framework.

**Next Topic:** # Requirement Gathering Process and Requirement Specification Documents

## Introduction

Before developing any software application, developers need to understand what they are building, why they are building it, and what users expect from it.

This is where **Requirement Gathering** comes into the Software Development Life Cycle (SDLC).

Requirement gathering is the process of identifying, collecting, analyzing, and documenting the needs and expectations of stakeholders before software development begins.

It helps the development team understand the actual problem they are solving instead of making assumptions about what the client wants.

For example, imagine a company wants to build an e-commerce application. Before writing Python code, creating Django models, or designing REST APIs, the team needs to understand:

- Who will use the application?
- What features should it provide?
- What problems should it solve?
- What performance and security expectations must it satisfy?
- Which features should be developed first?

These questions are addressed during requirements engineering.

---

## 1. Requirement Gathering Process

The requirement gathering process consists of six main steps.

### 1.1 Identify Stakeholders

A stakeholder is any individual, group, or organization that has an interest in the software or is affected by its development and operation.

Identifying stakeholders helps the development team understand whose needs and expectations must be considered.

**Examples of stakeholders in an e-commerce application:**

- Customers: Purchase products and track orders.
- Administrators: Manage users, products, and orders.
- Store owners: Monitor sales and manage inventory.
- Business managers: Define business goals.
- Developers: Implement and maintain the application.
- System administrators: Manage infrastructure and deployment.

Each stakeholder may have different expectations and priorities.

### 1.2 Establish Goals and Objectives

After identifying stakeholders, the team needs to understand what the organization wants to achieve.

Although goals and objectives are related, they have different meanings.

**Goals:**

- Broad outcomes the organization wants to achieve.
- Describe the overall direction or desired result.

**Objectives:**

- Specific actions or measurable results.
- Explain how the organization plans to achieve its goals.

**Example:**

- Goal: Improve the online shopping experience.
- Objective: Allow customers to search for products, add them to a cart, and complete purchases through a simple checkout process.

The distinction is important because broad goals need to be translated into clear, actionable objectives.

### 1.3 Elicit Requirements

Requirement elicitation is the process of collecting information about stakeholder needs and expectations.

Common techniques include:

- **Interviews:** Discuss requirements directly with stakeholders.
- **Surveys:** Collect information from multiple users.
- **Workshops:** Bring stakeholders together to discuss requirements.
- **Observation:** Study how users currently perform their tasks.
- **Document analysis:** Review existing business documents and systems.

**Example:**

During interviews, customers explain that they need:

- Product search and filtering.
- Shopping cart functionality.
- Secure payment processing.
- Order tracking.

These become candidate requirements for the application.

### 1.4 Document Requirements

After collecting requirements, the team organizes and records them in requirement specification documents.

Documentation ensures that stakeholders, developers, testers, and project managers share a common understanding of what needs to be built.

For example, requirements might describe:

- User registration and authentication.
- Product management.
- Shopping cart operations.
- Order processing.
- Payment integration.

### 1.5 Confirm Requirements

Requirements must be reviewed with stakeholders to ensure that they accurately represent their needs.

This step helps identify:

- Missing requirements.
- Incorrect assumptions.
- Ambiguous descriptions.
- Conflicting expectations.
- Requirements that are difficult to understand or implement.

**Example:**

The development team documents that customers can reset forgotten passwords.

During review, the client confirms that password reset links must be sent through email and expire after a limited period.

This clarification prevents misunderstandings before implementation.

### 1.6 Prioritize Requirements

Not every requirement has the same importance.

The team must determine which requirements should receive attention first, considering business value, user needs, cost, risk, and available resources.

**Example:**

| Priority | Requirements                                      |
| -------- | ------------------------------------------------- |
| High     | Registration, login, product browsing, checkout   |
| Medium   | Product reviews, order history                    |
| Low      | Product recommendations, advanced personalization |

Prioritization helps the team focus on essential functionality before implementing less critical features.

---

## 2. Goals vs. Objectives

These concepts are commonly confused.

| Goals                            | Objectives                              |
| -------------------------------- | --------------------------------------- |
| Broad outcomes                   | Specific results                        |
| Describe what we want to achieve | Describe measurable actions or outcomes |
| Provide overall direction        | Help achieve the goals                  |
| Usually less detailed            | More specific and measurable            |

**Example:**

Goal: Increase customer satisfaction.

Objective: Reduce the average checkout process to fewer than five steps.

A good objective should be clear and measurable whenever possible.

---

## 3. Types of Requirement Specification Documents

After gathering and analyzing requirements, organizations document them using different types of requirement specifications.

Three important documents are:

1. Software Requirements Specification (SRS).
2. User Requirements Specification (URS).
3. System Requirements Specification (SysRS).

Each document has a different scope and purpose.

### 3.1 Software Requirements Specification (SRS)

SRS describes the requirements of the software application.

It explains what the software must do, how it should behave, and what quality expectations it must satisfy.

It acts as an important reference for developers, testers, project managers, and other technical stakeholders.

An SRS commonly includes:

**A. Functional Requirements**

Describe the specific operations and services the software must provide.

Examples:

- Users can register and log in.
- Customers can add products to their shopping carts.
- Customers can place orders.
- Administrators can create, update, and delete products.

**B. Non-Functional Requirements**

Describe quality attributes and constraints that determine how well the software operates.

Examples:

- API responses should complete within two seconds under a specified workload.
- User passwords must be securely stored.
- The application must support a specified number of concurrent users.
- The system should remain available according to its availability target.

**C. External Interface Requirements**

Describe how the software communicates or interacts with external systems, users, or other components.

Examples:

- Integration with an external payment gateway.
- Communication with an email service.
- REST API communication with a frontend application.

**D. System Features**

Describe major groups of related software functionality.

Examples:

- User authentication.
- Product management.
- Order management.
- Payment processing.

An SRS may also contain:

- Performance requirements.
- Design and implementation constraints.
- Assumptions.
- Dependencies.
- Data requirements.
- Security requirements.

The exact organization and section names can vary depending on the project and specification standard being followed.

### 3.2 User Requirements Specification (URS)

URS focuses on what users and business stakeholders need from the system.

It describes requirements from the user's perspective without necessarily explaining the technical implementation.

A common way to express user requirements is through **User Stories**.

A user story generally follows this structure:

> As a [type of user], I want [some functionality], so that [some benefit].

**Example:**

"As a customer, I want to add products to my shopping cart so that I can purchase multiple products together."

Breaking it down:

| Part                                              | Meaning                      |
| ------------------------------------------------- | ---------------------------- |
| As a customer                                     | Who needs the functionality? |
| I want to add products to my cart                 | What do they need?           |
| So that I can purchase multiple products together | Why do they need it?         |

URS may also contain use cases, business needs, user expectations, and acceptance criteria.

**Acceptance Criteria**

Acceptance criteria define the conditions that must be satisfied for a requirement or feature to be accepted.

For the shopping cart example:

- Customers can add available products to their carts.
- Customers can update product quantities.
- Customers can remove products from their carts.
- The cart displays the correct total price.

These conditions help guide acceptance testing.

### 3.3 System Requirements Specification (SysRS)

SysRS describes requirements for the complete system rather than only the software.

A system can consist of multiple components, including software, hardware, people, procedures, and operational environments.

For an e-commerce platform, SysRS may cover:

| Category            | Example                                             |
| ------------------- | --------------------------------------------------- |
| Software            | Django backend and frontend application             |
| Hardware            | Servers with sufficient processing power and memory |
| Security            | Access control and data protection                  |
| Performance         | Support for expected concurrent users               |
| Personnel           | System administrators and support staff             |
| Policies            | Business and operational procedures                 |
| Regulations         | Applicable data protection regulations              |
| Acceptance criteria | Conditions required before system approval          |

The important idea is that a complete system is more than a software application.

It includes everything needed to operate the solution successfully.

---

## 4. Comparing SRS, URS, and SysRS

These three documents describe requirements from different perspectives.

| Document | Main Focus                 | Main Question                       |
| -------- | -------------------------- | ----------------------------------- |
| URS      | User and business needs    | What do users need and why?         |
| SRS      | Software requirements      | What must the software do?          |
| SysRS    | Entire system requirements | What does the complete system need? |

Consider the following example:

**URS — User Need**

A customer wants to purchase products online.

**SRS — Software Requirements**

The application must provide product browsing, shopping cart, checkout, and payment functionality.

**SysRS — System Requirements**

The complete solution requires software, servers, security mechanisms, personnel, and operational procedures.

These documents are related, but they are not interchangeable.

Their development is also iterative; teams may refine them together as they discover more about the project.

---

## 5. Connecting Requirements to Backend Development

Understanding requirements is especially important for backend developers because they translate business and user needs into technical functionality.

Let's use the following user story:

"As a customer, I want to add products to my shopping cart so that I can purchase them later."

As a Django REST Framework developer, we can translate this requirement into possible technical components.

| Requirement                   | Possible Backend Implementation          |
| ----------------------------- | ---------------------------------------- |
| Store products                | Django Product model                     |
| Store customer carts          | Django Cart model                        |
| Store cart items              | Django CartItem model                    |
| Add products to cart          | DRF API endpoint                         |
| Update product quantities     | DRF update endpoint                      |
| Validate product availability | Serializer validation and business logic |
| Restrict cart access          | Authentication and permissions           |

A possible API endpoint:

```http
POST /api/cart/items/
```

Request body:

```json
{
  "product_id": 15,
  "quantity": 2
}
```

The backend should:

1. Validate the incoming request.
2. Check whether the product exists.
3. Check product availability.
4. Associate the cart item with the authenticated customer.
5. Save the item in the database.
6. Return an appropriate response.

The key lesson is that the user requirement describes the desired outcome, while the software requirement defines what the application must provide to achieve that outcome.

The technical implementation is then designed to satisfy those requirements.

---

## 6. Important Takeaways

- Requirement gathering helps developers understand what they are building before implementation begins.
- Stakeholders are the people or organizations affected by the software.
- Goals describe broad outcomes, while objectives describe more specific results.
- Requirement elicitation collects information through interviews, surveys, workshops, observation, and other techniques.
- Requirements must be documented, confirmed, and prioritized.
- URS focuses on user and business needs.
- SRS focuses on software functionality and quality requirements.
- SysRS covers the entire system, including software, hardware, personnel, and procedures.
- Backend developers translate requirements into database models, API endpoints, validation rules, permissions, and business logic.

## Conclusion

Requirement gathering is one of the foundations of successful software development.

A developer should not focus only on how to implement a feature. They must first understand why the feature is needed, who needs it, and what behavior is expected.

As I continue my IBM Back-End Development Professional Certificate learning journey, understanding these concepts helps me connect the software development process with the practical work of designing and building backend applications using Python, Django, and Django REST Framework.

**Next Topic:** Software Development Methodologies.
