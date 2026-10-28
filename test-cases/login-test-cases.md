# Login Page – Manual Test Cases

**Application under test:** [Practice Test Automation – Test Login](https://practicetestautomation.com/practice-test-login/)  
**Valid credentials:** student / Password123  
**Test management:** test cases are also maintained in Qase (suite *Login Page*).

Priority: High = blocks login or exposes a security risk · Medium = wrong behaviour with a workaround · Low = cosmetic.  
Expected results marked **(to confirm)** are not stated on the page; the actual behaviour is recorded during execution.

---

## Positive test cases

### TC-P01: Login with valid credentials via Submit button

**Priority:** High · **Severity:** Critical · **Type:** Smoke  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | student | – |
| 3 | Type password into the Password field | Password123 | – |
| 4 | Click the Submit button | – | URL contains /logged-in-successfully/; page shows 'Congratulations' or 'successfully logged in'; Log out button is displayed |

### TC-P02: Login with valid credentials via Enter key

**Priority:** Medium · **Severity:** Normal · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | student | – |
| 3 | Type password into the Password field | Password123 | – |
| 4 | Press Enter while focus is in the Password field | – | Same result as TC-P01 (to confirm) |

### TC-P03: Log out after successful login

**Priority:** High · **Severity:** Critical · **Type:** Smoke  
**Preconditions:** User is logged in with student / Password123 and the success page is displayed.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Click the Log out button | – | User returns to the login page; Username and Password fields are empty |

### TC-P04: Password is masked while typing

**Priority:** High · **Severity:** Major · **Type:** Security  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type a password into the Password field | Password123 | Characters are shown as dots or asterisks, not as plain text |

### TC-P05: Successful login after a failed attempt

**Priority:** Medium · **Severity:** Normal · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Log in with username incorrectUser and password Password123 | incorrectUser / Password123 | Error 'Your username is invalid!' is displayed; user stays on the login page |
| 3 | Enter valid credentials and click Submit | student / Password123 | Login succeeds; the earlier error does not block the attempt |

### TC-P06: Keyboard navigation through the form

**Priority:** Low · **Severity:** Minor · **Type:** Usability  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Press Tab repeatedly | – | Focus moves Username -&gt; Password -&gt; Submit in that order |

---

## Negative test cases

### TC-N01: Invalid username, valid password

**Priority:** High · **Severity:** Critical · **Type:** Smoke  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | incorrectUser | – |
| 3 | Type password into the Password field | Password123 | – |
| 4 | Click the Submit button | – | Error 'Your username is invalid!' is displayed; user stays on the login page |

### TC-N02: Valid username, invalid password

**Priority:** High · **Severity:** Critical · **Type:** Smoke  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | student | – |
| 3 | Type password into the Password field | incorrectPassword | – |
| 4 | Click the Submit button | – | Error 'Your password is invalid!' is displayed; user stays on the login page |

### TC-N03: Invalid username and invalid password

**Priority:** High · **Severity:** Major · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | incorrectUser | – |
| 3 | Type password into the Password field | incorrectPassword | – |
| 4 | Click the Submit button | – | Login fails; one error message is shown (to confirm which one) |

### TC-N04: Both fields empty

**Priority:** High · **Severity:** Major · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Leave Username and Password empty | (empty) / (empty) | – |
| 3 | Click the Submit button | – | Login fails; an error message is shown (to confirm) |

### TC-N05: Empty username, valid password

**Priority:** Medium · **Severity:** Normal · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Leave Username empty and type the password | (empty) / Password123 | – |
| 3 | Click the Submit button | – | Error 'Your username is invalid!' is displayed; user stays on the login page |

### TC-N06: Valid username, empty password

**Priority:** Medium · **Severity:** Normal · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type the username and leave Password empty | student / (empty) | – |
| 3 | Click the Submit button | – | Error 'Your password is invalid!' is displayed; user stays on the login page |

### TC-N07: Username is case-sensitive

**Priority:** Medium · **Severity:** Normal · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | Student | – |
| 3 | Type password into the Password field | Password123 | – |
| 4 | Click the Submit button | – | Login fails with the username error (to confirm) |

### TC-N08: Password is case-sensitive

**Priority:** High · **Severity:** Major · **Type:** Security  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | student | – |
| 3 | Type password into the Password field | password123 | – |
| 4 | Click the Submit button | – | Error 'Your password is invalid!' is displayed; user stays on the login page |

### TC-N09: Leading and trailing spaces in username

**Priority:** Low · **Severity:** Minor · **Type:** Functional  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | ' student ' (with spaces) | – |
| 3 | Type password into the Password field | Password123 | – |
| 4 | Click the Submit button | – | Consistent behaviour: spaces are trimmed and login succeeds, or the username error is shown (to confirm) |

### TC-N10: SQL injection in username

**Priority:** High · **Severity:** Critical · **Type:** Security  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | ' OR '1'='1 | – |
| 3 | Type password into the Password field | anything | – |
| 4 | Click the Submit button | – | Login fails with an error; no database error or stack trace is shown |

### TC-N11: Script injection in username

**Priority:** High · **Severity:** Critical · **Type:** Security  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Type username into the Username field | &lt;script&gt;alert(1)&lt;/script&gt; | – |
| 3 | Type password into the Password field | anything | – |
| 4 | Click the Submit button | – | No alert pop-up appears; input is not rendered as HTML |

### TC-N12: Open success page without logging in

**Priority:** High · **Severity:** Critical · **Type:** Security  
**Preconditions:** User is not logged in. A new Incognito window is open.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Paste the success page URL into the address bar and press Enter | https://practicetestautomation.com/logged-in-successfully/ | User is redirected to the login page and cannot see the success page (to confirm) |

### TC-N13: Browser Back after Log out

**Priority:** Medium · **Severity:** Major · **Type:** Security  
**Preconditions:** User is logged in with student / Password123 and the success page is displayed.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Click the Log out button | – | Login page is displayed |
| 2 | Press the browser Back button | – | The success page is not shown again as a logged-in session (to confirm) |

---

## Regression test cases

**Smoke set** (run first after every build): TC-P01, TC-P03, TC-N01, TC-N02.

### TC-R01: Cross-browser login

**Priority:** High · **Severity:** Major · **Type:** Compatibility  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Run TC-P01, TC-N01 and TC-N02 in Chrome | Chrome latest | All three pass |
| 2 | Repeat in Firefox | Firefox latest | Same results as in Chrome |
| 3 | Repeat in Edge | Edge latest | Same results as in Chrome |

### TC-R02: Mobile viewport

**Priority:** Medium · **Severity:** Normal · **Type:** Compatibility  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open DevTools device mode and set width to 375 px | 375 px | Page reloads in mobile size |
| 2 | Run TC-P01 | student / Password123 | Form fits the screen without horizontal scroll; Submit is visible and clickable; login succeeds |

### TC-R03: Page labels and layout

**Priority:** Low · **Severity:** Minor · **Type:** Regression  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Compare the page with the last approved screenshot | – | Labels Username, Password and Submit and their positions are unchanged |

### TC-R04: Error message updates between attempts

**Priority:** Medium · **Severity:** Normal · **Type:** Regression  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Log in with incorrectUser / Password123 | incorrectUser / Password123 | Error 'Your username is invalid!' is displayed; user stays on the login page |
| 3 | Without reloading, log in with student / incorrectPassword | student / incorrectPassword | Only the password error is shown; the username error is gone |

### TC-R05: Page refresh after an error

**Priority:** Low · **Severity:** Minor · **Type:** Regression  
**Preconditions:** Browser is open. User is not logged in.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Log in with incorrectUser / Password123 | incorrectUser / Password123 | Error 'Your username is invalid!' is displayed; user stays on the login page |
| 3 | Refresh the page (F5) | – | Error message disappears; fields are empty |

### TC-R06: No JavaScript errors on page load

**Priority:** Medium · **Severity:** Normal · **Type:** Regression  
**Preconditions:** Browser is open. DevTools Console is open.

| # | Action | Test data | Expected result |
|---|---|---|---|
| 1 | Open the login page | https://practicetestautomation.com/practice-test-login/ | Login page is displayed with Username, Password and Submit |
| 2 | Check the Console tab | – | No JavaScript errors are shown |
