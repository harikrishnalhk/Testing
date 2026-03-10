day 1: https://www.notion.so/31e0387c9d9b80aca271fb715d22421d?source=copy_link
day 2: https://www.notion.so/Documents-Used-in-testing-31f0387c9d9b80c082c6d53e52dc1b0f?source=copy_link

DAY 1:
# 

# Software Testing – Fundamental

## 1. Ariane 5 Rocket Explosion (1996)

Ariane 5

### What Happened

The **Ariane 5 rocket** exploded **37 seconds after launch**.

### Root Cause

A **software conversion error** occurred.

A **64-bit floating point number** was converted into a **16-bit integer**, which caused an **overflow error**.

### Why Testing Failed

The software used was **copied from Ariane 4 rocket** without proper testing for Ariane 5 conditions.

### Damage

Loss of about **$370 million**.

### Lesson for Testers

Never reuse code without **testing under new conditions**.

---

# 2. Knight Capital Trading Disaster (2012)

Knight Capital Group

### What Happened

A deployment mistake caused the system to start **buying and selling stocks randomly**.

### Root Cause

An **old testing flag in the code was accidentally activated in production**.

The system executed millions of wrong trades.

### Impact

Loss of **$440 million in 45 minutes**.

### Testing Failure

- No proper **regression testing**
- Deployment configuration not verified
- No **production safety checks**

### Lesson

Testing must include **deployment validation**.

---

# 3. NASA Mars Climate Orbiter (1999)

Mars Climate Orbiter

NASA

### What Happened

The spacecraft was supposed to orbit Mars but instead **burned up in the atmosphere**.

### Root Cause

One software system used **metric units (Newton)** while another used **imperial units (Pound-force)**.

### Impact

Mission failure worth **$327 million**.

### Testing Failure

No **integration testing** between systems.

### Lesson

Integration testing is **critical when multiple systems interact**.

---

# 4. Healthcare.gov Website Crash (2013)

Healthcare.gov

### What Happened

The website launched for millions of Americans but **crashed immediately**.

### Problems

- Users couldn’t create accounts
- Pages froze
- Server crashes

### Root Cause

The system was **never tested with real traffic load**.

### Testing Failure

Lack of **performance and load testing**.

### Lesson

Always simulate **real user load** before release.

---

# 5. Apple iOS Autocorrect Bug

iOS

Apple

### What Happened

Many users saw the word **“I” autocorrected to “A[?]”** in messages.

Example

```
I love you → A[?] love you
```

### Root Cause

A bug in **text rendering logic**.

### Testing Failure

Edge cases in **text processing** were not tested.

### Lesson

Even **small UI bugs can affect millions of users**.

---

# 6. Facebook Outage (2021)

Meta Platforms

Facebook

Instagram

WhatsApp

### What Happened

All services went down globally for **6 hours**.

### Root Cause

A configuration change **broke internal network routing**.

### Impact

- Billions of users affected
- Estimated loss **$60 million+**

### Testing Failure

Infrastructure changes were **not validated in staging properly**.

### Lesson

Infrastructure changes must undergo **staging testing and rollback planning**.

---

# 7. Amazon Pricing Bug

Amazon

### What Happened

A pricing algorithm malfunction caused items to sell for **1 penny**.

Example

```
DVD worth $20 → sold for $0.01
```

### Impact

Huge losses for sellers.

### Testing Failure

Algorithm changes were **not validated with boundary testing**.

### Lesson

Edge case testing is extremely important.

## 1. What is Software Testing?

**Software Testing** is the process of **verifying and validating** a software application to ensure it works as expected and is free from defects.

### Objectives of Testing

- Find **bugs/defects**
- Ensure the software meets **business requirements**
- Verify **quality, performance, and security**
- Prevent **failures in production**

### Example

If a login page should allow users with **valid email and password** to login:

| Input | Expected Result | Actual Result | Status |
| --- | --- | --- | --- |
| valid email + password | login success | login success | Pass |
| invalid password | error message | page crash | Bug |

---

# 2. SDLC vs STLC

## SDLC (Software Development Life Cycle)

SDLC describes **how software is developed**.

### Phases of SDLC

1. Requirement Analysis
2. System Design
3. Development (Coding)
4. Testing
5. Deployment
6. Maintenance

### Flow

```
Requirement → Design → Development → Testing → Deployment → Maintenance
```

### Example

A company wants to build an **E-commerce website**

- Requirement → Product listing, cart, payment
- Design → Architecture, database design
- Development → Developers write code
- Testing → Testers validate features
- Deployment → Application released
- Maintenance → Bug fixes & improvements

---

## STLC (Software Testing Life Cycle)

STLC focuses only on **testing activities**.

### Phases of STLC

1. Requirement Analysis
2. Test Planning
3. Test Case Design
4. Test Environment Setup
5. Test Execution
6. Test Closure

### Flow

```
Requirement Analysis
        ↓
Test Planning
        ↓
Test Case Design
        ↓
Environment Setup
        ↓
Test Execution
        ↓
Test Closure
```

### Explanation

| Phase | Description |
| --- | --- |
| Requirement Analysis | Understand features to test |
| Test Planning | Decide strategy, tools, timelines |
| Test Case Design | Write test cases |
| Environment Setup | Setup servers, DB, tools |
| Test Execution | Run test cases |
| Test Closure | Prepare test reports |

---

# 3. Levels of Testing

Levels describe **where testing happens in the development process**.

### 1. Unit Testing

Testing **individual components or functions**.

Usually done by **developers**.

Example:

```
calculateTotalPrice()
```

Check if price calculation works correctly.

---

### 2. Integration Testing

Testing **interaction between modules**.

Example

```
Login Module → Dashboard Module
```

Verify login correctly redirects to dashboard.

---

### 3. System Testing

Testing the **entire application as a whole**.

Example

Testing complete **E-commerce workflow**

```
Login → Search product → Add to cart → Payment
```

---

### 4. Acceptance Testing (UAT)

Performed by **clients or business users**.

Purpose: Verify software meets **business needs**.

Example

Client checks if **order process works correctly** before release.

---

### Summary

| Level | Who Performs | What is Tested |
| --- | --- | --- |
| Unit | Developers | Individual functions |
| Integration | Dev/Testers | Module interaction |
| System | Testers | Entire system |
| Acceptance | Client | Business requirements |

---

# 4. Types of Testing

Testing can be categorized based on **what we test**.

---

## Functional Testing

Testing **application features and functionality**.

Focus:

```
Does the system work as expected?
```

Example

Login functionality:

- valid login
- invalid login
- forgot password

---

## Non-Functional Testing

Testing **system behaviour and quality attributes**.

Focus:

```
How well the system works
```

### Types

| Type | Purpose |
| --- | --- |
| Performance Testing | Speed and response |
| Load Testing | Behavior under many users |
| Stress Testing | Breaking point |
| Security Testing | Vulnerability detection |
| Usability Testing | User friendliness |

Example

Check if website handles **10,000 users simultaneously**.

---

# 5. Smoke vs Sanity vs Regression Testing

These are **common interview questions** for testers.

---

## Smoke Testing

**Basic testing to check if the build is stable.**

Done after a **new build is deployed**.

Purpose:

```
Check critical features quickly
```

Example

- Login works
- Dashboard loads
- Basic navigation works

If smoke test fails → **build rejected**

---

## Sanity Testing

Performed after **minor changes or bug fixes**.

Purpose:

```
Verify specific functionality works after fix
```

Example

Bug fixed in **payment page**

Test only:

- payment feature
- related modules

---

## Regression Testing

Testing **entire application after changes**.

Purpose:

```
Ensure new code didn't break old features
```

Example

After adding **coupon feature**, verify:

- login
- cart
- payment
- order history

---

### Quick Comparison

| Testing | Purpose | Scope |
| --- | --- | --- |
| Smoke | Check build stability | Very small |
| Sanity | Check specific change | Small |
| Regression | Ensure old features still work | Large |

---

# 6. Manual Testing vs Automation Testing

## Manual Testing

Testing performed **manually by testers** without scripts.

Example

Tester manually:

- enters input
- checks output
- reports bug

### Advantages

- Good for **exploratory testing**
- Easy to start
- No coding required

### Disadvantages

- Time consuming
- Repetitive work

---

## Automation Testing

Testing performed using **scripts/tools**.

Example Tools

- Selenium
- Cypress
- Playwright
- TestNG
- JUnit

Example

Automation script automatically:

```
Open browser
Enter login
Click submit
Verify dashboard
```

### Advantages

- Faster execution
- Reusable scripts
- Good for regression testing

### Disadvantages

- Initial setup time
- Requires programming knowledge

---

### Comparison

| Feature | Manual Testing | Automation Testing |
| --- | --- | --- |
| Speed | Slow | Fast |
| Human effort | High | Low |
| Cost | Low initially | High initially |
| Best for | Exploratory testing | Regression testing |

---

# 7. Agile Testing Overview

Traditional model → **Waterfall**

Modern companies → **Agile**

---

## What is Agile?

Agile is a **software development methodology** where development happens in **small iterations called sprints**.

Sprint duration usually:

```
2 weeks
```

---

## Agile Workflow

```
Product Backlog
      ↓
Sprint Planning
      ↓
Development
      ↓
Testing
      ↓
Sprint Review
      ↓
Release
```

---

## Role of Tester in Agile

Testers work **parallel with developers**.

Activities:

- Understand user stories
- Write test cases
- Test during development
- Perform regression testing
- Participate in sprint meetings

---

## Agile Ceremonies

| Ceremony | Purpose |
| --- | --- |
| Sprint Planning | Decide sprint tasks |
| Daily Standup | Daily progress discussion |
| Sprint Review |   |
| Retrospective | Improve process |

---

# Final Summary (Important for Juniors)

Testing ensures **software quality**.

Key concepts:

| Concept | Meaning |
| --- | --- |
| SDLC | Development process |
| STLC | Testing process |
| Levels of Testing | Unit → Integration → System → Acceptance |
| Functional Testing | Feature validation |
| Non-Functional Testing | Performance, security etc |
| Smoke Testing | Build verification |
| Sanity Testing | Verify specific change |
| Regression Testing | Ensure old features still work |
| Manual Testing | Human testing |
| Automation Testing | Script-based testing |
| Agile Testing | Continuous testing in sprints |

# Error vs Bug vs Defect vs Failure

These four terms represent **different stages of a problem in software**.

```
Human Mistake → Error
        ↓
Coding Problem → Bug
        ↓
Issue Found During Testing → Defect
        ↓
Problem Seen by User → Failure
```

---

# 1. Error

**Error** is a **human mistake made by a developer, tester, or designer**.

It happens during:

- requirement understanding
- design
- coding

### Example

A developer writes the wrong formula.

```
Total Price = Quantity + Price
```

Instead of

```
Total Price = Quantity × Price
```

The **wrong thinking or mistake made by the developer** is called an **Error**.

### Key Point

Error happens **before the code runs**.

---

# 2. Bug

A **Bug** is the **incorrect code written due to the error**.

Example code:

```
int total = quantity + price;
```

This wrong code is a **Bug**.

### Key Point

Bug = **Problem in the code**

Usually found during:

- development
- testing

---

# 3. Defect

A **Defect** is when the tester **finds a bug while testing and reports it**.

Example:

Tester tests the shopping cart.

```
Quantity = 2
Price = 100
```

Expected Result

```
Total = 200
```

Actual Result

```
Total = 102
```

Tester logs a defect in the bug tracking tool.

Common tools used:

- Jira
- Bugzilla
- Azure DevOps

### Key Point

Defect = **Bug identified and documented by tester**

---

# 4. Failure

A **Failure** happens when the **software behaves incorrectly for the end user**.

Example:

Customer buys product online.

Cart calculation shows:

```
Total = ₹102 instead of ₹200
```

Now the **system fails to meet user expectation**.

This visible issue is called **Failure**.

### Key Point

Failure happens **in the production environment**.

---

# Simple Real Life Example (Best for Teaching)

### Scenario: Calculator App

Developer makes a mistake.

```
Addition function
5 + 5 = 55
```

Step by step:

1️⃣ Developer misunderstood logic → **Error**

2️⃣ Wrong code written → **Bug**

3️⃣ Tester finds the issue and reports it → **Defect**

4️⃣ User sees wrong result in app → **Failure**

---

# Quick Comparison Table
DAY 2 :
# Documents Used in testing

# Authentication Module – Login & Register

---

# 1. BRD (Business Requirement Document)

## Objective

The system should allow users to create an account and securely access the application.

## Business Requirements

- Users should be able to **register** for a new account.
- Users should be able to **login** using registered credentials.
- Only **authenticated users** should access the dashboard.

---

# 2. SRS (Software Requirement Specification)

## Functional Requirements

### FR1 – User Registration

- User must enter:
    - Name
    - Email
    - Password
- Email must be unique.
- Password should be at least **6 characters**.

### FR2 – User Login

- User should login using:
    - Email
    - Password

### FR3 – Authentication Validation

- System should validate credentials.
- Invalid credentials should display an **error message**.

### FR4 – Successful Login

- After successful login, user should be redirected to the **dashboard**.

---

# 3. User Stories

## User Story 1 – Registration

**As a new user**, I want to create an account so that I can access the platform.

## User Story 2 – Login

**As a registered user**, I want to login so that I can use the application features.

---

# 4. Acceptance Criteria

## Registration

- User must provide **name, email, password**
- Email must be **unique**
- Password must contain **minimum 6 characters**
- Registration success message should appear

## Login

- User enters **valid email and password**
- System verifies credentials
- User is redirected to **dashboard**
- Invalid credentials should show **error message**

---

# 5. Test Plan

## Module

Authentication (Login & Register)

## Testing Scope

- User registration
- User login validation
- Error message validation

## Testing Types

- Functional testing
- Validation testing
- UI testing

---

# 6. Test Scenarios

## Registration Scenarios

- TS01 – Verify user registration with valid details
- TS02 – Verify registration with existing email
- TS03 – Verify password validation
- TS04 – Verify registration with empty fields

## Login Scenarios

- TS05 – Verify login with valid credentials
- TS06 – Verify login with invalid password
- TS07 – Verify login with unregistered email
- TS08 – Verify login with empty fields

---

# 7. Test Cases

## Registration Test Cases

### TC_REG_01 – Valid Registration

**Steps**

1. Enter name
2. Enter email
3. Enter password
4. Click register

**Expected Result**

User account should be created successfully.

---

### TC_REG_02 – Registration with Existing Email

**Steps**

1. Enter already registered email
2. Enter password
3. Click register

**Expected Result**

System should display **email already exists** error.

---

### TC_REG_03 – Registration with Weak Password

**Steps**

1. Enter password less than 6 characters

**Expected Result**

System should display **password validation error**.

---

## Login Test Cases

### TC_LOGIN_01 – Valid Login

**Steps**

1. Enter valid email
2. Enter valid password
3. Click login

**Expected Result**

User should be redirected to **dashboard**.

---

### TC_LOGIN_02 – Invalid Password

**Steps**

1. Enter valid email
2. Enter incorrect password

**Expected Result**

System should display **invalid credentials** message.

---

### TC_LOGIN_03 – Unregistered Email

**Steps**

1. Enter unregistered email
2. Enter password

**Expected Result**

System should show **user not found** error.

---

### TC_LOGIN_04 – Empty Fields

**Steps**

1. Click login without entering data

**Expected Result**

System should display **required field validation messages**.

---

# Complete Flow

```
BRD
↓
SRS
↓
User Stories
↓
Acceptance Criteria
↓
Test Plan
↓
Test Scenarios
↓
Test Cases

```
