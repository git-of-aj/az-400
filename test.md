Docs - https://learn.microsoft.com/en-us/azure/devops/pipelines/test/test-glossary?view=azure-devops

- LAB: https://microsoftlearning.github.io/AZ400-DesigningandImplementingMicrosoftDevOpsSolutions/Instructions/Labs/AZ400_M05_L09_Setting_Up_and_Running_Tests.html


1. Unit Tests test a single part of your application’s logic. One can further describe it by listing some of the things that it isn’t. A unit test doesn’t test how your code works with dependencies or infrastructure – that’s what integration tests are for.

### 1. **Unit Test:**
   - **Motives:** To test individual units or components of a software to ensure they function as designed.
   - **Benefits:** Early detection of bugs, aids in maintaining code quality, facilitates code refactoring.
   - **Example:** Testing a function that calculates the total price of items in a shopping cart.

### 2. **Integration Test:**
   - **Motives:** To verify interactions between integrated components or systems.
   - **Benefits:** Ensures that integrated components work together correctly, identifies issues in communication between modules.
   - **Example:** Testing the interaction between a database and the application layer to ensure data retrieval and storage.

### 3. **Functional Test:**
   - **Motives:** To validate that the software meets the specified requirements and functions as expected.
   - **Benefits:** Guarantees that the software performs its intended functions accurately.
   - **Example:** Testing a registration form to ensure that user data is stored correctly in the database.

### 4. **UI Test:**
   - **Motives:** To validate the graphical user interface (GUI) and ensure that it behaves as expected.
   - **Benefits:** Detects issues related to user interactions and interface design.
   - **Example:** Testing a button click event in a web application to ensure it triggers the intended action.

### 5. **Load Test:**
   - **Motives:** To evaluate the system's behavior under normal and peak load conditions.
   - **Benefits:** Identifies performance bottlenecks, helps in capacity planning.
   - **Example:** Simulating a large number of concurrent users accessing a website to assess server response times.

### 6. **Stress Test:**
   - **Motives:** To determine the system's stability and robustness under extreme conditions.
   - **Benefits:** Identifies how the system behaves beyond its normal operational capacity.
   - **Example:** Subjecting a server to a higher-than-normal load to see if it can handle the stress without crashing.

### 7. **Smoke Test:**
   - **Motives:** To quickly determine if the build is stable enough for more in-depth testing.
   - **Benefits:** Quickly identifies major issues, prevents wasting time on extensive testing of an unstable build.
   - **Example:** Testing critical functionalities of a newly developed feature before initiating comprehensive testing.

### When to Use:
- **Unit tests:** Use during development to ensure the correctness of individual units.
- **Integration tests:** Conduct after unit tests to validate the collaboration between integrated components.
- **Functional tests and UI tests:** Perform during the later stages of development to ensure the system meets specified requirements and has a user-friendly interface.
- **Load tests, stress tests, and smoke tests:** Execute during the testing and deployment phases to evaluate performance, stability, and overall system health.

Each type of test serves a specific purpose in ensuring the reliability and quality of software, and a combination of these tests contributes to a comprehensive testing strategy.
