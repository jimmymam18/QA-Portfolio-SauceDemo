# QA Portfolio: SauceDemo Manual Testing

- **Tester:** Veasna Mam | ISTQB CTFL
- **Application under test:** [SauceDemo (Swag Labs)](https://www.saucedemo.com), a public demo e-commerce site built for testing practice
- **Environment:** Google Chrome, macOS
- **Testing type:** Manual (functional and negative testing)

This repository contains test cases and a defect report I wrote and executed while practicing manual QA. Each test case follows a four-part structure: **Scenario**, **Steps**, **Data**, and **Expected Result**, and was compared against the **Actual Result** during execution.

---

## Test Cases: Login

### TC-01: Valid login with standard_user

| Field | Detail |
|---|---|
| **Scenario** | Valid login with standard_user |
| **Steps** | 1. Go to saucedemo.com<br>2. Enter username<br>3. Enter password<br>4. Click "Login" |
| **Data** | Username: `standard_user`<br>Password: `secret_sauce` |
| **Expected Result** | User is redirected to the Products page |
| **Actual Result** | User was redirected to the Products page |
| **Status** | Pass |

### TC-02: Invalid login attempt with locked_out_user

| Field | Detail |
|---|---|
| **Scenario** | Invalid login attempt with locked_out_user |
| **Steps** | 1. Go to saucedemo.com<br>2. Enter username<br>3. Enter password<br>4. Click "Login" |
| **Data** | Username: `locked_out_user`<br>Password: `secret_sauce` |
| **Expected Result** | An error message is displayed: "Epic sadface: Sorry, this user has been locked out." User stays on the login page. |
| **Actual Result** | Error message displayed: "Epic sadface: Sorry, this user has been locked out." User remained on the login page. |
| **Status** | Pass |

### TC-03: Invalid login attempt with empty password field

| Field | Detail |
|---|---|
| **Scenario** | Invalid login attempt with empty password field |
| **Steps** | 1. Go to saucedemo.com<br>2. Enter username<br>3. Leave the password field blank<br>4. Click "Login" |
| **Data** | Username: `standard_user`<br>Password: (blank) |
| **Expected Result** | An error message is displayed. User stays on the login page. |
| **Actual Result** | Error message displayed: "Epic sadface: Password is required." User remained on the login page. |
| **Status** | Pass |

---

## Defect Report

### BUG-01: Product images do not match product titles

| Field | Detail |
|---|---|
| **Title** | Product images do not match product titles; all items show the same incorrect image |
| **Steps to Reproduce** | 1. Go to saucedemo.com<br>2. Log in with username `problem_user` and password `secret_sauce`<br>3. Land on the Products page<br>4. Compare each product's image to its title |
| **Expected Result** | Each product displays an image that matches its title (for example, "Sauce Labs Backpack" shows a backpack). |
| **Actual Result** | Every product displays the same unrelated image (a dog), regardless of the product title. |
| **Environment** | Google Chrome, macOS |
| **Severity** | Medium |
| **Severity Rationale** | Affects every product and misrepresents what customers are buying, which damages trust. It does not block adding items to the cart or checking out, so it is not High. |

---

## Testing Notes

- **Scope judgment:** While logging in, Chrome's built-in Password Manager showed a "password found in a data breach" notification. This comes from the browser, not the application under test, so I did not log it as a defect.
- **Pass/Fail logic:** A test passes when the actual result matches the expected result. Negative tests (locked-out user, missing field) pass when the application correctly rejects the invalid input.

## In Progress

- Checkout flow test cases (required-field validation on First Name, Last Name, and Postal Code)

## Skills Demonstrated

Test case design, expected vs. actual result comparison, negative testing, defect reporting, severity assessment, and test scope awareness.
