🛒 Savana E-Commerce API Testing Portfolio
A comprehensive Black-Box API testing suite for the Savana e-commerce platform. This project demonstrates the reverse-engineering of live, undocumented web APIs and the application of formal software testing methodologies to validate core business logic, security, and system reliability.

📌 Project Overview
This repository contains a fully automated Postman test suite. Instead of testing standard dummy APIs, this project involved intercepting live network traffic, extracting required authentication headers and complex JSON payloads, and building automated assertion scripts to test the backend architecture of a production-level e-commerce application.

🛠️ Tools & Technologies
API Testing Tool: Postman

Scripting / Assertions: JavaScript (Chai Assertion Library)

Traffic Interception: Chrome DevTools (Network Tab, cURL parsing)

Data Format: JSON (Server-Driven UI architectures)

🧪 Testing Methodologies Applied
This suite bridges the gap between theoretical software testing and practical API automation. The following formal test design techniques were implemented:

Equivalence Partitioning (EP): Used for OTP validation, search queries, and unauthorized access blocking.

Boundary Value Analysis (BVA): Used to validate maximum inventory sync limits and order-split thresholds.

Decision Table Testing: Used for complex, multi-condition logic such as logistics/pincode serviceability and coupon code validation.

State Transition Testing: Used to verify database state changes and UI refresh triggers during the Cart Item lifecycle.

📂 Test Suite Breakdown
1. Functional Requirements (FRs)
Validating that the system performs its required business functions correctly.

FR_01_OTP_VALIDATION: Evaluates mobile number length constraints.

FR_02_PRODUCT_SEARCH: Validates structured inventory responses against valid and "no-result" partitions.

FR_03_CART_LIFECYCLE: Tests the state transition of items (Active vs. Removed).

FR_04_COUPON_RULES: Validates discount code application logic.

FR_05_ORDER_CALCULATION: Tests boundary thresholds that trigger split-order deliveries.

2. Critical Test Scenarios (CTS)
Ensuring the system is protected against edge cases and malicious inputs.

CTS_01_PRICE_MANIPULATION: Verifies the backend ignores untrusted client-side price injections and enforces database truth.

CTS_02_LOGISTICS_SERVICEABILITY: Validates the multi-rule decision table for shipping availability.

CTS_03_UNAUTHORIZED_ACCESS: Tests the API gateway's response to missing or tampered session tokens.

CTS_05_INVENTORY_LIMITS: Enforces strict upper boundaries on item quantities to prevent hoarding.

3. Non-Functional Requirements (NFRs)
Validating the performance, reliability, and security posture of the backend.

NFR_01_RELIABILITY: Verifies the system catches malformed payloads and returns a structured SDUI JSON error instead of crashing into an HTML 500 page.

NFR_02_SECURITY: Audits network headers to ensure sensitive server technologies (e.g., X-Powered-By) are not leaked.

NFR_03_PERFORMANCE: Enforces a strict response time Service Level Agreement (SLA) of < 500ms for critical transaction paths.

🚀 How to Use This ProjectClone the repository: git clone https://github.com/yourusername/savana-api-testing.git Import into Postman: Open Postman, click Import, and select the Savana_testing.postman_collection.json file.
Update Authentication: Production tokens are unique and expire quickly. 

To run these tests yourself, you must provide your own active session tokens. 

🔑 How to find your Login & Payment TokensSince these tokens are specific to your account session and expire frequently, 

follow these steps to retrieve them: Open Savana: Go to the Savana Website and log in to your account.

Open Developer Tools: Press F12 or Right-Click > Inspect and navigate to the Network tab.

Capture the Request: * For Login/OTP: Perform a login action. Look for a request named sendCode or login. 

For Payment/Checkout: Go to your bag and click "Checkout." 

Look for a request named previewOrder. Extract the Token:Click on the request and look at the Headers section. 

Find the key named token (or authorization). Copy the long alphanumeric string. 

Update Postman: In Postman, go to your Collection's Variables or Headers tab and paste your fresh token into the value field. 


🎓 Author
Ishanvi B.Tech Computer Science and Engineering | Bennett University

Passionate about software quality assurance, backend architecture, and competitive programming.
