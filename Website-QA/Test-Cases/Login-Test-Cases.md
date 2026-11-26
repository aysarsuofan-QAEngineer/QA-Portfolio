# Login Test Cases

## Application Information

- **Application:** SauceDemo
- **URL:** https://www.saucedemo.com/
- **Module:** Login
- **Testing Type:** Functional, Negative, UI, Usability, and Validation Testing

## Test Data

| User Type | Username | Password |
|---|---|---|
| Standard User | standard_user | secret_sauce |
| Locked Out User | locked_out_user | secret_sauce |
| Problem User | problem_user | secret_sauce |
| Performance Glitch User | performance_glitch_user | secret_sauce |
| Invalid User | invalid_user | invalid_password |

## Test Cases

### 1. Positive Login Scenarios

| ID | Test Scenario | Preconditions | Test Steps | Test Data | Expected Result | Priority | Test Type |
|---|---|---|---|---|---|---|---|
| TC-001 | Login with valid credentials | Login page is displayed | Enter valid username and password, then click Login | standard_user / secret_sauce | User should be redirected to the Products page | High | Positive |
| TC-002 | Login with valid credentials using Enter key | Login page is displayed | Enter valid credentials and press Enter | standard_user / secret_sauce | User should be logged in successfully | High | Functional |
| TC-003 | Login with valid credentials after refreshing the login page | Login page is displayed | Refresh the page, enter valid credentials, and click Login | standard_user / secret_sauce | User should be logged in successfully | Medium | Functional |
| TC-004 | Login with valid credentials using different supported user accounts | Login page is displayed | Enter valid credentials for another supported user | problem_user / secret_sauce | User should be redirected to the Products page | Medium | Functional |

### 2. Negative Login Scenarios

| ID | Test Scenario | Preconditions | Test Steps | Test Data | Expected Result | Priority | Test Type |
|---|---|---|---|---|---|---|---|
| TC-005 | Login with invalid password | Login page is displayed | Enter a valid username and invalid password, then click Login | standard_user / wrong_password | An appropriate error message should be displayed | High | Negative |
| TC-006 | Login with invalid username | Login page is displayed | Enter an invalid username and valid password, then click Login | invalid_user / secret_sauce | An appropriate error message should be displayed | High | Negative |
| TC-007 | Login with invalid username and password | Login page is displayed | Enter invalid username and password, then click Login | invalid_user / invalid_password | An appropriate error message should be displayed | High | Negative |
| TC-008 | Login with locked-out user | Login page is displayed | Enter locked-out user credentials and click Login | locked_out_user / secret_sauce | An error message should indicate that the user is locked out | High | Negative |
| TC-009 | Login with empty username and password | Login page is displayed | Leave both fields empty and click Login | Empty / Empty | A validation error should be displayed | High | Validation |
| TC-010 | Login with empty username | Login page is displayed | Leave username empty, enter password, and click Login | Empty / secret_sauce | A validation error should indicate that username is required | High | Validation |
| TC-011 | Login with empty password | Login page is displayed | Enter username, leave password empty, and click Login | standard_user / Empty | A validation error should indicate that password is required | High | Validation |
| TC-012 | Login with username containing only spaces | Login page is displayed | Enter spaces in username and a valid password, then click Login | "   " / secret_sauce | Login should not succeed and an appropriate error should be displayed | Medium | Validation |
| TC-013 | Login with password containing only spaces | Login page is displayed | Enter a valid username and spaces in password, then click Login | standard_user / "   " | Login should not succeed and an appropriate error should be displayed | Medium | Validation |
| TC-014 | Login with username containing special characters | Login page is displayed | Enter special characters as username and click Login | @#$%^ / secret_sauce | Login should not succeed and an appropriate error should be displayed | Medium | Negative |
| TC-015 | Login with password containing special characters | Login page is displayed | Enter a valid username and special characters as password, then click Login | standard_user / @#$%^ | Login should not succeed and an appropriate error should be displayed | Medium | Negative |

### 3. Input Field Validation

| ID | Test Scenario | Preconditions | Test Steps | Test Data | Expected Result | Priority | Test Type |
|---|---|---|---|---|---|---|---|
| TC-016 | Verify username field accepts text input | Login page is displayed | Enter text in the username field | standard_user | Username should be entered correctly | Medium | UI |
| TC-017 | Verify password field accepts text input | Login page is displayed | Enter text in the password field | secret_sauce | Password should be entered correctly | Medium | UI |
| TC-018 | Verify password masking | Login page is displayed | Enter a password in the password field | secret_sauce | Password characters should be masked | High | Security |
| TC-019 | Verify username field accepts long input | Login page is displayed | Enter a long string in the username field | 100-character string | The field should handle the input without breaking the page | Low | Validation |
| TC-020 | Verify password field accepts long input | Login page is displayed | Enter a long string in the password field | 100-character string | The field should handle the input without breaking the page | Low | Validation |
| TC-021 | Verify username field retains entered value after failed login | Login page is displayed | Enter a valid username and invalid password, then click Login | standard_user / wrong_password | Username should remain populated after the failed attempt | Medium | Functional |
| TC-022 | Verify password field behavior after failed login | Login page is displayed | Enter invalid credentials and click Login | standard_user / wrong_password | Password field should be cleared or handled according to the application behavior | Medium | Functional |
| TC-023 | Verify leading and trailing spaces in username | Login page is displayed | Enter a username with spaces before and after it, then click Login | " standard_user " / secret_sauce | Application should handle the input consistently and should not authenticate incorrectly | Medium | Validation |

### 4. UI and Usability Testing

| ID | Test Scenario | Preconditions | Test Steps | Test Data | Expected Result | Priority | Test Type |
|---|---|---|---|---|---|---|---|
| TC-024 | Verify login page elements are displayed | Login page is opened | Observe the login page | N/A | Username, password, Login button, and application branding should be displayed | High | UI |
| TC-025 | Verify username field placeholder | Login page is displayed | Inspect the username field | N/A | Username field should display the expected placeholder | Low | UI |
| TC-026 | Verify password field placeholder | Login page is displayed | Inspect the password field | N/A | Password field should display the expected placeholder | Low | UI |
| TC-027 | Verify Login button is enabled | Login page is displayed | Observe the Login button | N/A | Login button should be enabled and clickable | High | UI |
| TC-028 | Verify login error message visibility | Login page is displayed | Submit invalid credentials | standard_user / wrong_password | Error message should be clearly visible to the user | High | Usability |
| TC-029 | Verify login error message can be closed | An error message is displayed | Click the error message close icon | N/A | Error message should disappear | Medium | Functional |
| TC-030 | Verify login page layout on browser resize | Login page is displayed | Resize the browser window | N/A | Login page elements should remain visible and usable | Medium | UI |

### 5. Navigation and Session Testing

| ID | Test Scenario | Preconditions | Test Steps | Test Data | Expected Result | Priority | Test Type |
|---|---|---|---|---|---|---|---|
| TC-031 | Verify navigation after successful login | Login page is displayed | Enter valid credentials and click Login | standard_user / secret_sauce | User should be redirected to the Products page | High | Navigation |
| TC-032 | Verify login page reload behavior | Login page is displayed | Refresh the browser page | N/A | Login page should reload without unexpected errors | Medium | Functional |
| TC-033 | Verify browser back navigation after login | User is logged in successfully | Navigate to the Products page, then click browser Back | standard_user / secret_sauce | Application should handle navigation without exposing an invalid or inconsistent state | Medium | Navigation |
| TC-034 | Verify direct access to Products page without login | User is logged out | Open the Products page URL directly | https://www.saucedemo.com/inventory.html | User should be redirected to the login page or denied access | High | Security |
| TC-035 | Verify login behavior after logging out | User has logged in and logged out | Log out, then attempt to access the Products page | N/A | User should not be able to access protected content without logging in again | High | Session |

## Execution Notes

- All test cases must be executed before assigning final statuses.
- Record actual results and attach screenshots when applicable.
- Report any unexpected behavior as a defect.
- Do not mark unexecuted test cases as Passed.
- Test results should be updated in the Test Execution Report.
