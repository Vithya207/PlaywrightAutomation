**Overview**
This document provides an overview and explanation of the automated test script adminTests.spec.js, which is part of a Playwright test suite for managing room-related functionalities in an admin web application. The tests cover a range of CRUD (Create, Read, Update, and Delete) operations for rooms, including validation checks and language localization support.

**Test Structure**
  The adminTests.spec.js file includes the following key components:
**1. Imports and Setup**
  Playwright Modules: Import test, expect, and chromium from Playwright for test running, assertions, and browser control.
  Page Objects: Import LoginPage, RoomsPage, and RoomDetailsPage for encapsulating page interactions.
  Fixture Data: Import test data from data.json.
**2. Global Variables**
  Browser, Context, and Page: Manage browser instance, context, and page for test navigation and actions.
  Page Objects: Instances of page objects (roomsPage, roomDetailsPage, and login) to interact with the application.
**3. Test Suite Definition**
Defined using test.describe, it encapsulates all related test cases.
**Hooks**
•	beforeAll: Sets up the environment by launching the browser, creating a context and page, and logging into the admin panel.
•	beforeEach: Ensures that a fresh context and page are available for each test, preventing state leakage between tests.
•	afterAll: Cleans up resources by closing the browser and context.
**Test Cases**
  1. Admin Delete Room
    o	Tests deleting rooms specified in the data.delete array and verifies their removal.
  2. Admin Create Room
    o	Tests creating rooms using valid data from data.create.valid and verifies their presence.
  
  3. Admin Update Room
   o	Tests updating existing room details using data from data.update and verifies the updates.
  4. Admin Create Room - Field Level Validations
   o	Tests form validation for creating rooms with invalid data from data.create.invalid.
  5. Admin Update Room - Field Level Validation (Localization)
   o	Tests field-level validation during room updates with invalid data (data.updateinvalid) across multiple languages (en and de). It iterates over the supported languages and ensures error messages are appropriately displayed.

**Running the Tests**
To run the test suite, use the following command:
**npx playwright test adminTests.spec.js --project chromium**
This will execute all the test cases defined in the file.
**Running Tests in Headed Mode**
By default, Playwright runs tests in headless mode (without a visible UI). To run the tests with the browser UI visible, use:
**npx playwright test adminTests.spec.js –headed**

**Reporting and Screenshots**
Below lists of reports are configured.
**Line, list, dot, Html and Allure**
To generate allure report, use the following command
**allure generate allure-results -o allure-report –clean
allure open allure-report**

**Defect report is attached in the repository**

