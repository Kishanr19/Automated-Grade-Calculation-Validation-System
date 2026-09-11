# Automated Grade Calculation & Validation System

**Hackathon Project**

A Java application designed to automate peer-assessment processing, validate structured evaluation inputs and calculate individual grade outcomes through deterministic grading logic.

Developed within a **5-person hackathon team**, with an emphasis on **modular software design, input validation, 10+ unit tests, debugging, Git/GitHub version control, CI/CD and iterative software delivery**.

---

## Project Overview

Group assessments can require individual grades to be adjusted according to peer-evaluation data, creating a process that can become repetitive and difficult to apply consistently when handled manually.

This project converts that workflow into repeatable application logic.

The system accepts structured peer-assessment inputs, validates the supplied data, processes individual evaluation values and applies defined calculation rules to generate individual grade outcomes.

Rather than coupling input handling directly to grade calculations, the application separates **validation, processing, calculation and result generation** into distinct responsibilities.

```text
Peer-Assessment Input
          │
          ▼
    Input Validation
          │
          ▼
    Data Processing
          │
          ▼
 Grade Calculation
          │
          ▼
   Result Validation
          │
          ▼
 Individual Outcomes
```

This approach was designed to keep the core calculation behaviour **predictable, testable and maintainable** as functionality evolved throughout the hackathon.

---

## Engineering Highlights

| Area                        | Implementation                                                                             |
| --------------------------- | ------------------------------------------------------------------------------------------ |
| **Application Development** | Built a working Java application for automated assessment processing and grade calculation |
| **Team Development**        | Developed and integrated functionality within a 5-person hackathon team                    |
| **Algorithmic Design**      | Translated assessment requirements into deterministic calculation logic                    |
| **Validation**              | Validated structured inputs before applying grade-processing rules                         |
| **Unit Testing**            | Developed 10+ unit tests covering calculation behaviour and input scenarios                |
| **Edge-Case Testing**       | Tested boundary and unexpected inputs to identify failures in calculation logic            |
| **Debugging**               | Traced failed scenarios to their source, corrected implementation logic and verified fixes |
| **Version Control**         | Used Git and GitHub to manage, integrate and track source-code changes                     |
| **CI/CD**                   | Used CI/CD practices to validate integrated changes and maintain a working build           |
| **Software Design**         | Separated validation, processing, calculation and result-generation responsibilities       |
| **Iterative Delivery**      | Developed, tested and integrated functionality throughout a time-constrained hackathon     |

---

## Core Functionality

The application automates the transformation of peer-assessment data into individual grade outcomes.

The end-to-end workflow consists of:

1. Receiving structured peer-assessment inputs.
2. Validating assessment values before processing.
3. Processing evaluation data for individual group members.
4. Applying deterministic grade-calculation rules.
5. Generating individual grade outcomes.
6. Validating calculated results against expected behaviour.

The objective was not simply to produce a calculation that worked for a single example. The implementation was designed so the same calculation process could be **repeated consistently across different combinations of assessment inputs**.

---

## Software Design

### Modular Processing

The assessment workflow was separated into distinct stages rather than implementing the entire process as one tightly coupled operation.

```text
Input
  │
  ├── Validation
  │
  ├── Processing
  │
  ├── Calculation
  │
  └── Result Generation
```

Separating these responsibilities made it easier to:

* isolate implementation defects;
* validate inputs independently;
* modify calculation behaviour;
* test specific stages of the workflow;
* debug incorrect outputs; and
* extend functionality without redesigning the complete application.

### Deterministic Calculation Logic

Assessment requirements were translated into explicit Java calculation logic.

For a given valid set of inputs, the application applies the same defined processing rules to produce a consistent result.

This made calculation behaviour easier to **reason about, reproduce and verify through testing**.

### Defensive Input Validation

Assessment data originates from user-provided values and therefore cannot automatically be assumed to be valid.

Validation was incorporated before the main calculation stage so unexpected or invalid values could be identified before affecting downstream grade-processing logic.

Keeping validation separate from calculation logic also made failures easier to diagnose during testing.

---

## Testing & Quality Engineering

Software quality formed part of the development process rather than being treated as a final check after implementation.

The project included **10+ unit tests** covering the application's calculation behaviour and different assessment scenarios.

Testing focused on:

* expected peer-assessment inputs;
* grade-calculation behaviour;
* different combinations of evaluation values;
* boundary conditions;
* edge cases;
* invalid or unexpected inputs;
* consistency of calculated results; and
* regression checking following code changes.

The development cycle followed a repeatable quality process:

```text
Implement
    │
    ▼
Unit Test
    │
    ▼
Identify Failure
    │
    ▼
Debug
    │
    ▼
Implement Fix
    │
    ▼
Retest
    │
    ▼
Integrate
```

When a test exposed unexpected behaviour, the affected processing or calculation stage was isolated before changes were made.

The corrected functionality was then retested to verify the fix and reduce the risk of introducing regressions elsewhere in the application.

---

## Debugging & Root-Cause Analysis

Debugging focused on identifying the **source of incorrect behaviour**, rather than changing calculations until the final output appeared correct.

For failed scenarios, the processing path could be traced through:

**Input → Validation → Processing → Calculation → Output**

This helped determine whether unexpected behaviour originated from input handling, data processing or the underlying calculation logic.

Once identified, implementation changes were tested against the original failing scenario before being integrated.

This **identify → isolate → fix → verify** approach supported more systematic debugging throughout development.

---

## Git & Version Control

**Git and GitHub** were used throughout development to manage source-code changes and support collaborative development within the 5-person team.

The development workflow followed an iterative pattern:

```text
Implement
    ↓
Test
    ↓
Debug
    ↓
Commit
    ↓
Integrate
    ↓
Validate
```

Version control provided a shared history of implementation changes and allowed functionality to be integrated into the common codebase throughout the hackathon.

Using Git also supported incremental development rather than relying on a single final integration of independently developed functionality.

---

## CI/CD & Integration

CI/CD practices were used alongside version control to support the integration and validation of code changes.

Changes progressed through development and testing before integration, helping maintain a working application as functionality evolved.

```text
Code Change
     │
     ▼
Local Validation
     │
     ▼
Unit Tests
     │
     ▼
Version Control
     │
     ▼
CI/CD Validation
     │
     ▼
Integration
```

Combining **Git, automated testing and CI/CD** helped introduce a more structured delivery workflow despite the limited hackathon timeframe.

---

## Collaborative Development

The application was developed within a **5-person hackathon team**.

Working within a shared codebase required functionality to be developed in a way that could be integrated with work produced by other team members.

This involved:

* breaking the overall problem into manageable development tasks;
* implementing functionality against agreed requirements;
* managing changes through Git and GitHub;
* testing functionality before integration;
* resolving implementation issues as functionality was combined; and
* maintaining focus on delivery within the hackathon deadline.

The constrained development window required technical decisions to balance **functionality, reliability and delivery speed**.

---

## Hackathon Delivery

The project progressed from initial requirements to a functioning application within the hackathon timeframe.

The overall engineering lifecycle was:

**Requirements → Design → Implementation → Testing → Debugging → Integration → Validation → Delivery**

Development therefore involved more than implementing the core calculation algorithm.

The team also had to determine how the requirements should be represented in software, structure the application, validate inputs, test behaviour, resolve defects and integrate functionality into a working final solution.

The limited timeframe encouraged **iterative delivery and prioritisation of core functionality** over unnecessary complexity.

---

## Engineering Challenges

### Translating Requirements into Application Logic

The central engineering challenge was converting a human assessment process into explicit and repeatable software behaviour.

Peer-assessment information represents human-generated evaluation data, while the application requires clearly defined rules.

The problem therefore had to be decomposed into:

**Input → Validation → Processing → Calculation → Output**

Breaking the workflow into these stages made individual behaviours easier to implement and test.

### Maintaining Calculation Reliability

Different combinations of peer-assessment values could exercise different parts of the calculation logic.

The application therefore needed to behave predictably beyond a single successful test case.

The **10+ unit tests**, combined with edge-case testing and debugging, were used to verify behaviour across multiple scenarios and identify calculation defects before final delivery.

### Integrating Development Within a Team

Hackathon development required multiple contributors to work against a shared deadline.

Git/GitHub version control, testing and CI/CD practices helped structure how changes were integrated and validated while the application continued to evolve.

---

## Technical Skills Demonstrated

The project provides practical evidence across several areas of software engineering:

### Software Development

* Java application development
* Modular software design
* Algorithmic problem-solving
* Requirements-to-code translation
* Data processing
* Deterministic business logic

### Software Quality

* 10+ unit tests
* Input validation
* Edge-case testing
* Regression checking
* Debugging
* Root-cause analysis
* Defect verification

### Development & Delivery

* Git
* GitHub
* Version control
* CI/CD
* Code integration
* Iterative development

### Engineering Collaboration

* 5-person development team
* Shared codebase development
* Technical problem-solving
* Integration of functionality
* Deadline-driven software delivery

---

## Technology Stack

| Technology / Practice | Purpose                                              |
| --------------------- | ---------------------------------------------------- |
| **Java**              | Core application and calculation logic               |
| **Git**               | Source-code version control                          |
| **GitHub**            | Repository and collaborative code management         |
| **Unit Testing**      | Verification of calculation and validation behaviour |
| **CI/CD**             | Validation and integration of application changes    |

---

## Production Evolution

The hackathon implementation prioritised delivery of the core calculation and validation workflow.

If the application were developed further towards a production service, potential engineering improvements would include:

* expanding automated unit and integration test coverage;
* persistent relational data storage;
* REST API endpoints separating clients from calculation services;
* structured exception and error handling;
* automated CI/CD quality gates;
* containerised execution;
* structured application logging;
* production monitoring and observability;
* authentication and role-based access control;
* configuration-driven grading rules; and
* deployment to managed cloud infrastructure.

These represent **future production-engineering improvements and are not claimed as functionality of the current implementation**.

---

## Key Outcomes

* Delivered a working **end-to-end Java application** within the hackathon deadline.
* Developed the solution collaboratively within a **5-person team**.
* Automated peer-assessment processing and individual grade calculation.
* Implemented validation around structured assessment inputs.
* Developed **10+ unit tests** covering calculation and input scenarios.
* Debugged calculation failures and edge cases before final delivery.
* Used **Git and GitHub version control** throughout development.
* Applied **CI/CD practices** to support integration and validation.
* Maintained a modular structure designed around testable application responsibilities.

---

## Repository

**Source Code:**
`github.com/Kishanr19/-Peer-Evaluation-System-for-Academic-Group-Assessment`

---

## Author

**Kishan Ravikumar**
BSc Computer Science — University of Essex
