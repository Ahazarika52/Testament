# Testament
All testing Brainstorming, Application Usage, Tools and Implementations

📌 Overview

Testament is a hybrid QA automation portfolio showcasing UI automation, API testing, and framework implementations using Selenium and Playwright.
It demonstrates real-world test strategies, CI/CD integration, and reporting capabilities for professional-grade testing workflows.

🎯 Objectives

Show proficiency in Selenium and Playwright for UI testing.

Implement Page Object Model (POM) for scalability.

Integrate API testing and database validation into automation.

Demonstrate cross-browser and cross-platform testing.

Provide interactive reports for stakeholders.

Implement CI/CD pipelines for continuous testing.

🛠️ Tech Stack
Category	Tools
UI Automation	Selenium WebDriver, Playwright
Language	Java (Selenium), JavaScript/TypeScript (Playwright)
Test Runner	TestNG (Java), Playwright Test Runner (TS)
API Testing	Postman, REST Assured
Reporting	Allure Reports, Extent Reports, Mochawesome
CI/CD	GitHub Actions, Jenkins
Package Manager	Maven (Java), npm (Node.js)
Others	WebdriverManager, dotenv, Faker.js
📂 Project Structure
📦 testament
 ┣ 📂 selenium-framework
 ┃ ┣ 📂 src
 ┃ ┃ ┣ 📂 main/java/pages   # Page Objects
 ┃ ┃ ┣ 📂 main/java/utils   # Utilities & Helpers
 ┃ ┃ ┣ 📂 test/java/tests   # Test Cases
 ┃ ┗ pom.xml                # Maven dependencies
 ┣ 📂 playwright-framework
 ┃ ┣ 📂 tests               # Playwright tests
 ┃ ┣ 📂 pages               # POM files
 ┃ ┣ 📂 utils               # Helpers & configs
 ┃ ┣ package.json           # npm dependencies
 ┃ ┗ playwright.config.ts   # Config file
 ┣ 📂 reports               # Allure/Mochawesome Reports
 ┣ 📂 docs                  # Documentation, diagrams, mind maps
 ┗ README.md

🚀 Selenium Framework Details
Key Features

Language: Java

Test Runner: TestNG

Design Pattern: Page Object Model (POM)

Dependency Management: Maven

Cross-browser support (Chrome, Firefox, Edge)

Data-driven testing via Excel/CSV/JSON

Integrated Allure & Extent reporting

Setup
# Clone repo
git clone https://github.com/yourusername/testament.git
cd selenium-framework

# Install dependencies
mvn clean install

# Run tests
mvn test

Sample Test
@Test
public void googleSearchTest() {
    driver.get("https://www.google.com");
    driver.findElement(By.name("q")).sendKeys("Hello Jerry", Keys.RETURN);
    Assert.assertTrue(driver.getTitle().contains("Hello Jerry"));
}

⚡ Playwright Framework Details
Key Features

Language: TypeScript

Test Runner: Playwright Test Runner

Design Pattern: POM for maintainability

Cross-browser testing (Chromium, Firefox, WebKit)

Parallel execution & retries

HTML & Mochawesome reports

Setup
# Go to Playwright project
cd playwright-framework

# Install dependencies
npm install

# Run tests
npx playwright test

# Run tests in headed mode
npx playwright test --headed

Sample Test
import { test, expect } from '@playwright/test';

test('Google Search Test', async ({ page }) => {
  await page.goto('https://www.google.com');
  await page.fill('input[name="q"]', 'Hello Jerry');
  await page.keyboard.press('Enter');
  await expect(page).toHaveTitle(/Hello Jerry/);
});

📈 Reporting
Selenium Reports

Allure Reports:

mvn allure:serve


Extent Reports: Auto-generated in reports/extent.html

Playwright Reports

HTML report:

npx playwright show-report

🔄 CI/CD Integration

GitHub Actions: Runs both Selenium & Playwright tests on every push.

Jenkins Pipeline: Nightly regression runs + email reports.

GitHub Actions Example:

name: Testament CI

on: [push, pull_request]

jobs:
  selenium-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          java-version: '17'
      - run: mvn test -f selenium-framework/pom.xml

  playwright-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '18'
      - run: npm install --prefix playwright-framework
      - run: npx playwright test --prefix playwright-framework

📜 Test Coverage

UI Tests

Login flows

Form validations

Navigation & broken links

API Tests

GET, POST, PUT, DELETE

Schema validation

DB Verification

SQL queries after UI/API actions

🧠 Learning & Brainstorming Section

Test Design Mind Maps

Bug Reports

Improvement Ideas

Post-mortem Notes

📬 Contact

Author: (Anshuman Prasad Hazarika)

LinkedIn:

GitHub: Anshu Man

Email: ahazarika52@gmail.com



