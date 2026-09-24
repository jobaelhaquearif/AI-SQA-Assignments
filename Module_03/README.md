MODULE 03 — ASSIGNMENT  
Software Testing Life Cycle (STLC) with AI  
Name: MD Jobael Haque (Arif) ID: 01675979838 Batch: 21  
Course: AI Driven SQA — Manual & Automation Testing \| OSTAD

## Q1. Test Plan — Online Shopping Website

Objective: confirm that the shopping website's core customer journey —
registration, login, product search, cart, and checkout — is
functionally correct, secure against basic misuse, and usable across
common browsers and devices.

Test Objectives

• Confirm business-critical shopping functions against approved
requirements.

• Validate positive, negative, boundary and error-handling scenarios.

• Confirm critical customer journeys remain stable across supported
browsers and devices.

## 1. Scope & Coverage

| Test Area               | Coverage                                                                                           |
|-------------------------|----------------------------------------------------------------------------------------------------|
| Login                   | Valid/invalid credentials, required-field checks, session handling, logout, lockout behaviour.     |
| Registration            | Field validation, password rules, duplicate-account handling, terms acceptance, verification flow. |
| Product Search & Browse | Keyword/category search, filters, sorting, empty-result handling.                                  |
| Cart                    | Add/remove/update items, quantity limits, price recalculation, stock checks.                       |
| Checkout & Payment      | Address entry, delivery options, discount codes, payment method selection, order confirmation.     |
| Order Confirmation      | Order ID generation, summary accuracy, confirmation messaging.                                     |

Out of scope: third-party payment provider internals, production server
administration, and features not yet released to QA.

## 2. Test Strategy

| Technique                   | Purpose                                                                                                         | Priority |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------|----------|
| Functional Testing          | Confirm each feature behaves as specified for valid, everyday customer actions.                                 | High     |
| Negative & Boundary Testing | Use invalid, missing, extreme, or edge-case inputs to confirm the system fails safely and clearly.              | High     |
| Integration Testing         | Verify handoffs between login, catalog, cart, checkout, and payment components work together correctly.         | High     |
| End-to-End Testing          | Walk a full customer journey — browse to registration to checkout — to confirm the whole flow holds together.   | High     |
| Regression Testing          | Re-run priority tests after each fix or release to confirm nothing that worked before has broken.               | High     |
| Usability Testing           | Check that labels, error messages, and navigation are clear enough for a first-time shopper.                    | Medium   |
| Compatibility Testing       | Confirm the site behaves consistently across supported browsers and screen sizes.                               | Medium   |
| Security Spot-Checks        | Probe login/registration inputs for basic injection and data-exposure risks.                                    | Medium   |
| AI-Assisted Test Design     | Use AI to draft scenario lists and edge cases quickly; a QA engineer reviews and adjusts every item before use. | Medium   |

## 3. Test Environment & Data

| Item              | Planned Setup                                                                                                             |
|-------------------|---------------------------------------------------------------------------------------------------------------------------|
| Test Environment  | Isolated QA/staging environment, separate from production data and traffic.                                               |
| Browsers          | Latest stable Chrome, Firefox, and Edge, plus one mobile browser (Chrome Android or Safari iOS).                          |
| Devices           | One desktop resolution and one representative mobile viewport, per the supported device matrix.                           |
| Test Accounts     | Valid registered user, newly created user, duplicate-email user, and a locked/invalid-credential account.                 |
| Test Data         | Valid and invalid addresses, in-stock and out-of-stock products, valid and expired discount codes, sandbox payment cards. |
| External Services | Sandbox/mock payment gateway; no real transactions are processed during testing.                                          |

## 4. Entry & Exit Criteria

| Gate           | Criteria                                                                                                                                                                        |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Entry Criteria | Build is deployed to QA; requirements are stable enough to test; required test accounts and data exist; test environment is reachable.                                          |
| Exit Criteria  | All high-priority test cases executed; no open blocker or critical defects; failed cases triaged and either fixed or accepted as known issues; results documented for sign-off. |

## 5. Roles & Responsibilities

| Role                       | Responsibility                                                                                 |
|----------------------------|------------------------------------------------------------------------------------------------|
| QA Engineer                | Writes and executes test cases/checklists, logs defects, retests fixes, reports status.        |
| QA Lead                    | Owns test strategy and coverage decisions, manages risk trade-offs, reports to stakeholders.   |
| Developer                  | Fixes reported defects, clarifies implementation behaviour, supports root-cause investigation. |
| Product Owner              | Clarifies requirements, prioritises business risk, signs off on acceptance criteria.           |
| DevOps / Environment Owner | Keeps the QA environment, test data, and deployment pipeline available and stable.             |

## 6. Risks & Mitigation

| Risk                                          | Impact                                           | Mitigation                                                                                    |
|-----------------------------------------------|--------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Payment gateway sandbox is unavailable        | Blocks end-to-end checkout validation.           | Use a mock/stub response for the payment step; test the surrounding flow independently.       |
| Test environment is unstable                  | Causes false failures and wastes execution time. | Log environment incidents separately from product defects; re-run only after a confirmed fix. |
| Requirements are incomplete or ambiguous      | Leads to disagreement on expected results.       | Confirm expected behaviour with the Product Owner before finalising test cases.               |
| Limited time for regression                   | Existing features may silently break.            | Prioritise regression around the highest-traffic flows: login, cart, and checkout.            |
| Test data becomes stale or reused incorrectly | Produces misleading pass/fail results.           | Maintain a small, controlled, reset-able set of test accounts and products.                   |

## 7. Defect Management

Every defect is logged with steps to reproduce, expected vs. actual
result, severity, and supporting evidence (screenshot/log).

Defects are triaged jointly with development and the Product Owner
before a fix is scheduled.

Every fix is retested, and a short regression pass covers the
surrounding functionality.

Release readiness is judged by unresolved risk, not just by raw defect
count.

AI use & human review: AI tools may be used to draft test ideas, edge
cases, or documentation faster. However, interpreting requirements,
judging real business risk, validating the test environment, and signing
off on quality remain the QA engineer's responsibility — not the AI's.

## Q2. Test Checklist

Each feature below is covered by 20 validation points using the required
columns: Test Area, Validation Point, and Expected Result.

## A. Login Checklist

| ID    | Test Area                       | Validation Point                                                             | Expected Result                                                                          |
|-------|---------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| LG-01 | Required fields                 | Submit the login form with both fields empty.                                | Both fields show a required-field message; no login attempt is sent.                     |
| LG-02 | Valid login                     | Enter a correct, registered email/username and password.                     | User is authenticated and lands on the expected post-login page.                         |
| LG-03 | Wrong password                  | Enter a valid email with an incorrect password.                              | Login is rejected with a generic error, without confirming which field was wrong.        |
| LG-04 | Unregistered account            | Enter an email that has never been registered.                               | Login fails with the same generic message used for a wrong password.                     |
| LG-05 | Invalid email format            | Enter text that is not a valid email pattern.                                | Format error appears before any server round-trip, where client-side validation exists.  |
| LG-06 | Empty password only             | Leave the password blank with a valid email entered.                         | Password-required message appears; login is blocked.                                     |
| LG-07 | Password masking                | Type a password into the field.                                              | Characters are masked by default (dots/asterisks).                                       |
| LG-08 | Show/hide password toggle       | Use the eye icon if the field provides one.                                  | Toggling reveals/hides the password without altering the typed value.                    |
| LG-09 | Case sensitivity                | Enter the registered email in a different letter case.                       | Email is treated as case-insensitive (standard expectation) unless documented otherwise. |
| LG-10 | Leading/trailing spaces         | Enter the email with extra spaces before or after it.                        | Input is trimmed automatically, or a clear validation message appears.                   |
| LG-11 | Repeated failed attempts        | Submit wrong credentials several times in a row.                             | Account lockout or throttling behaviour triggers per the security policy, if one exists. |
| LG-12 | SQL/script injection attempt    | Enter a string like ' OR 1=1-- into the login fields.                        | Input is treated as plain text; no error page or unexpected behaviour occurs.            |
| LG-13 | Session after logout            | Log out, then press the browser Back button.                                 | The previous authenticated page is not shown; login is required again.                   |
| LG-14 | Direct URL access               | While logged out, paste a direct URL to an account-only page.                | User is redirected to the login page instead of seeing protected content.                |
| LG-15 | Remember-me option              | Select "Remember Me" (if available), close and reopen the browser.           | Session persists or expires exactly as the feature is documented to behave.              |
| LG-16 | Session timeout                 | Stay idle past the configured timeout, if one is defined.                    | Session expires and the next action requires re-authentication.                          |
| LG-17 | Keyboard-only navigation        | Tab through the login form without using a mouse.                            | Focus order is logical; the form can be fully completed and submitted via keyboard.      |
| LG-18 | Field labels for screen readers | Inspect email/password fields with a screen reader or accessibility checker. | Each field has an associated, descriptive label.                                         |
| LG-19 | Mobile layout                   | Open the login page on a small mobile viewport.                              | Fields, buttons, and error text remain fully visible with no overlap.                    |
| LG-20 | Auto fill behavior              | Use the browser's saved-password auto fill.                                  | Auto filled credentials populate correctly and can still be edited before submit.        |

## B. Registration Checklist

| ID    | Test Area                          | Validation Point                                                          | Expected Result                                                                      |
|-------|------------------------------------|---------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| RG-01 | Required fields                    | Submit the form with all mandatory fields empty.                          | Each mandatory field shows its own required-field message.                           |
| RG-02 | Valid registration                 | Fill all fields correctly with a new email and submit.                    | Account is created, or a verification step begins, exactly as designed.              |
| RG-03 | Invalid email format               | Enter an email missing the @ symbol or domain.                            | Format validation blocks submission before an account is created.                    |
| RG-04 | Duplicate email                    | Register using an email that already has an account.                      | Registration is blocked with a clear "already registered" message.                   |
| RG-05 | Weak password                      | Enter a password that fails the stated complexity rule.                   | The specific unmet rule is shown; submission is blocked.                             |
| RG-06 | Password/confirm mismatch          | Enter different values in Password and Confirm Password.                  | Mismatch is flagged; the account is not created.                                     |
| RG-07 | Password/confirm match             | Enter identical, valid values in both password fields.                    | Validation passes and registration proceeds.                                         |
| RG-08 | Minimum length boundary            | Enter a password exactly at, and one character below, the minimum length. | The below-minimum case is rejected; the exact-minimum case is accepted.              |
| RG-09 | Maximum length boundary            | Enter a name/email far longer than the field is expected to allow.        | Input is truncated, rejected, or safely handled — never causes a server error.       |
| RG-10 | Invalid characters in name         | Enter numbers or symbols into a name field, if only letters are expected. | Field either blocks the invalid characters or the rule is confirmed as not enforced. |
| RG-11 | Phone number format                | Enter a phone number with letters or an incorrect number of digits.       | Validation catches the malformed number before submission.                           |
| RG-12 | Terms not accepted                 | Leave the Terms & Conditions checkbox unticked and submit.                | Registration is blocked until the box is checked.                                    |
| RG-13 | Terms accepted                     | Tick the checkbox with otherwise valid data and submit.                   | Registration proceeds without the terms error.                                       |
| RG-14 | Email/OTP verification             | Complete registration where a verification step is required.              | Account is fully active only after the verification code/link is confirmed.          |
| RG-15 | Expired or wrong verification code | Enter an expired or incorrect verification code.                          | Verification fails with a message and a clear way to request a new code.             |
| RG-16 | Injection-style input              | Enter script-like text into a text field.                                 | Text is stored/displayed literally; no script executes.                              |
| RG-17 | Copy-paste with extra spaces       | Paste a name or email with leading/trailing whitespace.                   | Whitespace is trimmed automatically or flagged clearly.                              |
| RG-18 | Password field exposure            | Watch the password field while typing and on page inspection.             | Value is masked on screen and not visible in plain text in the page source.          |
| RG-19 | Mobile layout                      | Complete registration on a small mobile viewport.                         | All fields, validation messages, and buttons remain usable without clipping.         |
| RG-20 | Keyboard accessibility             | Complete the entire form using only Tab and Enter.                        | Every field and the submit button are reachable in a logical order.                  |

## C. Checkout Checklist

| ID    | Test Area                           | Validation Point                                                   | Expected Result                                                                       |
|-------|-------------------------------------|--------------------------------------------------------------------|---------------------------------------------------------------------------------------|
| CO-01 | Checkout with valid cart            | Open checkout with an in-stock item already in the cart.           | Checkout loads with the correct item, quantity, and price.                            |
| CO-02 | Empty cart checkout                 | Try to reach checkout with an empty cart.                          | Checkout is blocked, or the customer is redirected with a clear empty-cart message.   |
| CO-03 | Missing address                     | Submit the order without entering a shipping address.              | Required-field validation appears; the order is not placed.                           |
| CO-04 | Valid address                       | Enter a complete, correctly formatted shipping address.            | Address is accepted and displayed correctly in the order summary.                     |
| CO-05 | Incomplete address                  | Enter an address missing a required part (e.g. postal code).       | Validation identifies the missing field before submission.                            |
| CO-06 | Delivery option selection           | Choose an available delivery method.                               | Selected option and its fee/timeframe are reflected in the order total.               |
| CO-07 | Delivery fee recalculation          | Switch between two different delivery options.                     | Order total updates immediately to match the newly selected option.                   |
| CO-08 | Order summary accuracy              | Compare the checkout summary against the actual cart contents.     | Items, quantities, and unit prices match exactly.                                     |
| CO-09 | Quantity change at checkout         | Increase or decrease an item's quantity, if editable at this step. | Subtotal and stock availability are re-validated correctly.                           |
| CO-10 | Item goes out of stock mid-checkout | Simulate an item becoming unavailable before payment.              | Customer is clearly notified; the unavailable item cannot be purchased.               |
| CO-11 | Valid discount code                 | Apply a currently valid promotional code.                          | Discount is applied correctly and the new total is shown immediately.                 |
| CO-12 | Invalid or expired discount code    | Apply a code that is wrong, expired, or already used.              | Code is rejected with a clear message; the total remains unchanged.                   |
| CO-13 | Payment method selection            | Select each available payment method in turn.                      | The correct next steps/fields appear for whichever method is selected.                |
| CO-14 | Payment failure handling            | Use a test card or scenario designed to fail.                      | Order is not confirmed; customer sees a clear failure message and can retry.          |
| CO-15 | Successful payment                  | Complete payment using an approved sandbox success scenario.       | Payment succeeds and the flow proceeds to order confirmation.                         |
| CO-16 | Double-click on Place Order         | Click or tap the Place Order button rapidly more than once.        | Only one order is created; the second click is safely ignored.                        |
| CO-17 | Session expires during checkout     | Let the session time out, then attempt to place the order.         | Customer is prompted to re-authenticate; no order is created without a valid session. |
| CO-18 | Grand total accuracy                | Manually add item total, delivery fee, discount, and tax (if any). | Displayed grand total matches the manual calculation exactly.                         |
| CO-19 | Order confirmation details          | Complete a successful order.                                       | Confirmation page/email shows a unique order ID and an accurate summary.              |
| CO-20 | Mobile checkout usability           | Complete the full checkout flow on a mobile viewport.              | Every step remains legible and operable without horizontal scrolling or overlap.      |

Final QA note: this checklist goes beyond the happy path — it includes
negative, boundary, security-lite, and accessibility checks. Before
execution, map each point to the site's actual approved requirements and
supported browser/device list.
