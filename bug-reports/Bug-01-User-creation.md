**Title**
Duplicate usernames allowed when trailing spaces are appended (Missing Input Trimming)


**Description:** 
The system allows registering users with duplicate usernames if leading spaces are added to the input field. The system stores the value as-is in the database without trimming, which bypasses the username uniqueness validation. 

**Steps to Reproduce:**
1. Go to the User Registration page.
2. Create a user with Username: "test" and click "create user".
3. Attempt to create another user with Username: "test " (note the space at the end) using a different email.
4. Observe that the user creation succeeds.

**Environment:**
Windows 11
Microsoft edge browser
 
**Expected Result:**
All text inputs (such as username) should be automatically trimmed before validation and database persistence. The system should reject "test " as a duplicate of "test".

**Actual Result:**
The backend saves "test " as a separate distinct username, allowing duplicate logical accounts in the database.

**Severity:** High

<img width="841" height="579" alt="Image" src="https://github.com/user-attachments/assets/1a05d319-3557-409d-891c-c1d597f44729" />

<img width="952" height="428" alt="Image" src="https://github.com/user-attachments/assets/3c611586-d705-48f9-8eff-e82d8e66c145" />
