
# Login Test Cases

## Application
SauceDemo - https://www.saucedemo.com/

## Module
Login

## Test Cases

| ID | Test Scenario | Test Steps | Expected Result | Priority |
|---|---|---|---|---|
| TC-001 | Login with valid credentials | Enter valid username and password, then click Login | User should be redirected to the Products page | High |
| TC-002 | Login with invalid password | Enter valid username and invalid password | An error message should be displayed | High |
| TC-003 | Login with invalid username | Enter invalid username and valid password | An error message should be displayed | High |
| TC-004 | Login with empty fields | Click Login without entering credentials | Validation error should be displayed | Medium |
| TC-005 | Login with locked user | Enter locked_out_user credentials | An error message should indicate that the user is locked out | High |
| TC-006 | Password masking | Enter a password in the password field | Password should be masked | Low |
