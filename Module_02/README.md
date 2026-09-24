MODULE 2 — ASSIGNMENT  
Software Development Life Cycle (SDLC) in the Age of AI  
Submitted by: MD Jobael Haque (Arif)  
Course: AI Driven SQA — Manual & Automation Testing \| OSTAD

## Q1. SDLC Lifecycle Diagram & Workflow Explanation

Workflow explanation:

Requirement Analysis — the team talks to stakeholders to find out what
the business and users need. These needs are written down as functional
and non-functional requirements in a BRD/SRS. AI can help by summarizing
meeting notes into a first draft of the requirements.

Design — once requirements are approved, the team plans how the system
will be built. This includes the High-Level Design (overall system) and
Low-Level Design (module details), plus database, API, and UI/UX design.
AI can suggest a first draft of the architecture or database schema,
which the team then checks and adjusts.

Implementation — Developers write the actual code, following the
approved design. They also do unit testing and use Git for version
control. AI coding tools like GitHub Copilot or Cursor AI can suggest
code as it is written, saving time on repetitive parts.

Testing — QA checks that the software works the way it should and finds
any defects before release. This includes test case design, defect
reporting, and regression testing. AI can help generate test cases or
sample test data, but a human still needs to check that the important
scenarios are covered.

Deployment — the tested software is released to the live environment,
along with smoke testing and monitoring. AI-based monitoring tools can
help spot unusual activity (for example, a sudden spike in failed
transactions) faster than checking logs manually.

Maintenance — after release, the team fixes bugs, applies security
updates, and improves the software based on user feedback. AI can help
by pointing out patterns in past issues, similar to how a support team
keeps track of common customer complaints.

## Q2. Practical AI Exercise

2.1. Question: Generate five user stories for an E-commerce
application.  
Five User Stories: E-Commerce Application

AI tool used: Claude (Anthropic).

| ID    | Feature                  | User Story                                                                                                                                                                |
|-------|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| US-01 | Product Search           | As a customer, I want to search products by keyword and category, so that I can quickly find the items I want to buy.                                                     |
| US-02 | Shopping Cart            | As a customer, I want to add items to a shopping cart, so that I can purchase multiple products in a single checkout.                                                     |
| US-03 | Multiple Payment Methods | As a customer, I want to pay using multiple payment methods (card, mobile banking, or cash on delivery), so that I can choose whichever option is most convenient for me. |
| US-04 | Order Tracking           | As a customer, I want to track my order status in real time, so that I know when to expect delivery.                                                                      |
| US-05 | Inventory Management     | As an admin, I want to manage product inventory (add, edit, or remove stock), so that customers only see items that are actually available.                               |

2.2. Question: Convert one user story into at least five acceptance
criteria.  
Acceptance Criteria (Story \#1 : Product Search)

Story \#1 — Product Search

User Story As a customer, I want to search products by keyword and
category, so that I can quickly find the items I want to buy.

| ID    | Scenario                | Acceptance Criterion                                                                                                                                                                |
|-------|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AC-01 | Search by Keyword       | Given a customer is on the product search page, when they enter a valid product keyword, then the system should display products matching the keyword.                              |
| AC-02 | Search by Category      | Given a customer selects a product category, when the search is performed, then the system should display products available in that category.                                      |
| AC-03 | No Matching Product     | Given a customer enters a keyword that does not match any product, when the search is completed, then the system should display a clear message that no matching product was found. |
| AC-04 | Relevant Search Results | Given a customer searches for a product, when the results are displayed, then the results should be relevant to the entered keyword or selected category.                           |
| AC-05 | View Product Details    | Given a customer receives search results, when they select a product, then the system should open the product details so the customer can review the product before purchasing.     |

QA Coverage The criteria cover positive search, category filtering,
no-result handling, result relevance and product-detail access.

2.3. Question: Ask the AI to create a Sprint Backlog  
AI-Generated Sprint Backlog

Product Search Epic

Epic Focus Build and validate a reliable product search experience that
allows customers to find products by keyword and category.

| Task ID | Backlog Item                                 | Owner                            | Estimate (SP) | Priority |
|---------|----------------------------------------------|----------------------------------|---------------|----------|
| PS-01   | Define product search requirements           | Business Analyst / Product Owner | 3             | High     |
| PS-02   | Design search and filter UI                  | UI/UX Designer                   | 3             | High     |
| PS-03   | Develop keyword search functionality         | Backend Developer                | 5             | High     |
| PS-04   | Implement category-based search              | Backend Developer                | 5             | High     |
| PS-05   | Develop search results UI                    | Frontend Developer               | 5             | High     |
| PS-06   | Handle no-result search scenarios            | Frontend Developer               | 3             | Medium   |
| PS-07   | Write & execute search functional test cases | QA Engineer                      | 5             | High     |
| PS-08   | Automate product search regression tests     | QA Automation Engineer           | 5             | Medium   |
| PS-09   | Perform end-to-end search testing            | QA Engineer                      | 3             | High     |
| PS-10   | Conduct UAT for product search               | QA / Product Owner               | 3             | High     |

Backlog Review

High-priority items focus on the core product-search journey and its QA
validation.

Negative scenarios include no-result handling.

QA work covers functional, regression and end-to-end testing.

UAT confirms that the completed search flow meets customer and business
expectations.

Story-point estimates are planning estimates and should be reviewed
against the team's actual capacity and velocity.

Backlog Alignment User Story → Acceptance Criteria → Sprint Backlog → QA
Validation → UAT

## 2.4. Review of AI-Generated Output & Manual Improvements

What the AI did well

Generated five user stories using the standard “As a \[role\], I want
\[goal\], so that \[benefit\]” structure.

Converted the selected story into Given/When/Then acceptance criteria.

Produced a sprint backlog with task IDs, owners, story-point estimates
and priorities.

Created a useful starting structure quickly, reducing the time needed to
organize the exercise.

Corrections and improvements made manually

| Area                | Manual Improvement                                                                                                                            |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Acceptance criteria | Separated keyword and category search into two independently testable scenarios.                                                              |
| Negative coverage   | Added a clear no-results criterion and refined the backlog to remove invalid-search handling that was not covered by the acceptance criteria. |
| Testability         | Refined the result-relevance criterion so that each displayed result must satisfy the selected search condition.                              |
| Backlog priority    | Kept requirements and core QA validation at High priority because the feature depends on clear requirements and end-to-end verification.      |
| Traceability        | Aligned the backlog with the selected Product Search story and its acceptance criteria.                                                       |

Why human review is still necessary

AI does not know the actual product catalog, category rules, search
logic or business priorities unless these are provided.

AI can produce confident-looking output while missing edge cases or
using requirements that are too broad.

Story-point estimates and priorities are planning suggestions and need
to be checked against the team's real capacity and velocity.

Human review is required to confirm correctness, testability, business
fit and overall software quality.

## 2.5. Screenshots of AI Interaction

Screenshot (I) — Claude Interaction: Five E-commerce User Stories  
Actual Claude conversation showing the prompt used to generate five
e-commerce user stories and the generated response.

Screenshot (II) — Claude Interaction: Acceptance Criteria and Sprint
Backlog  
Actual Claude conversation showing the prompt used to generate five
acceptance criteria and the Sprint Backlog for User Story \#1 — Product
Search.

Note: Due to the length of the AI-generated response, Screenshot 2 was
captured across three continuous sections to ensure the complete output
is included.
