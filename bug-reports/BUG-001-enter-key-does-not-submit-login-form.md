# BUG-001: Pressing Enter in the Password field does not submit the login form

| Field | Value |
|---|---|
| Severity | Minor |
| Priority | Medium |
| Status | Open |
| Environment | Windows 11, Chrome 156.0.8078.49 |
| Found in | TC-P02 |
| Date | 2026-10-27 (reproduced on 2026-10-28) |
| Reproducibility | Always (2/2 attempts) |

## Preconditions
Browser is open. User is not logged in.

## Steps to reproduce
1. Open https://practicetestautomation.com/practice-test-login/
2. Type `student` into the Username field
3. Type `Password123` into the Password field
4. With the cursor still in the Password field, press **Enter**

## Expected result
The form is submitted, the same as clicking Submit: the user is redirected to `/logged-in-successfully/` and the Log out button is displayed.

## Actual result
Nothing happens. The page does not change, the fields keep their values, and no error message or hint is shown. The user can log in only by clicking the Submit button.

## Impact
Most users expect Enter to submit a login form. Keyboard-only users and users of assistive technology may not be able to log in without a mouse.

## Attachments
<img width="1360" height="768" alt="image" src="https://github.com/user-attachments/assets/bd64c72a-4a65-4a8a-a746-3c2f641bc81c" />


## Notes
Clicking Submit with the same data works as expected (TC-P01 passed).
