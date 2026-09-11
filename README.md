# Peer Evaluation System

**Hackathon Software Engineering Project**

A Java application for processing peer-assessment data and calculating individual grade outcomes from group evaluation inputs.

Built under hackathon constraints with an emphasis on **modular design, deterministic calculation logic, input validation, testing, debugging, Git-based version control and iterative delivery**.

## Engineering Overview

The project converts a manual peer-assessment workflow into repeatable application logic.

Rather than coupling input handling directly to grade calculations, the implementation was designed around distinct responsibilities for processing assessment data, applying calculation rules and producing results.

```text
Assessment Input
       │
       ▼
Input Processing
       │
       ▼
Validation
       │
       ▼
Grade Calculation Logic
       │
       ▼
Result Generation
```

This structure was chosen to make the core calculation behaviour easier to **debug, test and extend** as requirements changed during the hackathon.

## Technical Skills Demonstrated

| Area                          | Implementation                                                                                   |
| ----------------------------- | ------------------------------------------------------------------------------------------------ |
| **Application Development**   | Implemented working application functionality in Java                                            |
| **Algorithmic Design**        | Converted peer-assessment requirements into deterministic grade-calculation logic                |
| **Data Processing**           | Transformed structured assessment inputs into individual grade outcomes                          |
| **Validation**                | Checked assessment inputs before applying calculation logic                                      |
| **Testing**                   | Evaluated calculation behaviour across different input and edge-case scenarios                   |
| **Debugging**                 | Diagnosed implementation and calculation defects during iterative development                    |
| **Version Control**           | Used Git and GitHub to manage and integrate code changes                                         |
| **Collaborative Development** | Integrated functionality within a shared codebase under hackathon time constraints               |
| **Software Design**           | Separated processing, calculation and output responsibilities to keep functionality maintainable |

## Core Functionality

The system processes peer-assessment information for members of an academic group and applies defined calculation rules to generate individual grade outcomes.

The core workflow consists of:

1. Receive structured peer-assessment inputs.
2. Validate the supplied assessment values.
3. Process evaluation data for each group member.
4. Apply the grade-calculation rules.
5. Generate individual grade outcomes.
6. Verify results against expected behaviour.

The focus was not simply producing a calculation that worked for one example, but implementing logic that could be repeatedly applied to different assessment inputs.

## Software Design

### Separation of Responsibilities

The implementation separates the major stages of the assessment workflow rather than treating the entire calculation as a single operation.

This makes it easier to:

* isolate defects;
* modify calculation behaviour;
* validate inputs independently;
* test individual stages of the workflow; and
* extend functionality without rewriting the entire application.

### Deterministic Business Logic

Academic assessment rules were translated into explicit application logic.

For a given valid set of inputs, the calculation process is designed to produce a consistent output. This made expected behaviour easier to reason about and test during development.

### Defensive Input Handling

User-provided assessment data introduces the possibility of invalid or unexpected values.

Input handling was therefore treated separately from the calculation itself so incorrect data could be identified before affecting grade-processing logic.

## Testing & Quality

Quality was treated as part of implementation rather than only checking whether the final application executed.

Testing focused on:

* expected assessment inputs;
* different combinations of peer evaluations;
* boundary and edge cases;
* incorrect or unexpected values;
* consistency of calculated outputs; and
* regression checking following changes.

When defects were identified, the affected logic was isolated, corrected and retested against relevant scenarios.

This **test → diagnose → fix → verify** cycle was used throughout development.

## Debugging

Debugging focused on tracing incorrect outputs back through the processing and calculation stages.

Instead of modifying calculations until the final value appeared correct, issues were isolated to the relevant part of the workflow and verified against expected behaviour after correction.

This helped maintain predictable behaviour as the implementation evolved.

## Version Control & Collaborative Development

**Git and GitHub** were used to manage source-code changes during the hackathon.

The development workflow involved:

```text
Implement
    ↓
Test
    ↓
Review / Debug
    ↓
Commit
    ↓
Integrate
    ↓
Verify
```

Using version control provided a shared history of changes and supported integration of functionality developed during the limited hackathon window.

## Hackathon Delivery

The project was developed within a constrained timeframe, requiring technical scope to be prioritised around delivering working functionality.

The development process involved:

**Requirements → Design → Implementation → Testing → Debugging → Integration → Delivery**

This required balancing implementation quality against the limited development window and prioritising functionality necessary for a working end-to-end solution.

## Engineering Challenges

### Translating Requirements into Software

The primary challenge was converting a real assessment process into explicit application behaviour.

Peer evaluations represent human-generated information, while software requires deterministic rules. The project therefore required the assessment requirements to be decomposed into data-processing and calculation steps that could be implemented and tested independently.

### Handling Edge Cases

Calculation functionality needed to remain predictable across different combinations of assessment inputs.

Testing multiple scenarios exposed cases that required additional validation or changes to calculation behaviour.

### Integrating Changes Under Time Constraints

Hackathon development required functionality to be implemented and integrated quickly without losing control of the shared codebase.

Git-based version control and iterative testing helped keep changes manageable while the application evolved.

## Skills Demonstrated

This project provides practical evidence of:

* **Java application development**
* **Git and GitHub version control**
* **Software testing and quality assurance**
* **Debugging and root-cause analysis**
* **Algorithmic problem-solving**
* **Input validation**
* **Modular software design**
* **Requirements-to-code translation**
* **Collaborative development**
* **Iterative software delivery**
* **Edge-case handling**
* **Technical decision-making**

## Production Evolution

The hackathon implementation deliberately prioritised core functionality. If developed further towards a production-style service, the next engineering steps would include:

* automated unit and integration test suites;
* persistent relational storage;
* REST API endpoints separating client and calculation services;
* stronger validation and structured error handling;
* automated CI/CD checks;
* containerised execution;
* application logging and monitoring;
* authentication and role-based access control;
* configuration-driven grading rules; and
* deployment to a managed cloud environment.

These are **future engineering improvements**, rather than capabilities claimed by the current implementation.

## Repository

**Source Code:**
`github.com/Kishanr19/-Peer-Evaluation-System-for-Academic-Group-Assessment`

## Author

**Kishan Ravikumar**
BSc Computer Science — University of Essex
