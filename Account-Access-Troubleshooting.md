# IT Lab 1 – Account & Access Troubleshooting (Windows)

## Goal
Show hands-on experience with basic help desk tasks related to user accounts, access issues, and password troubleshooting.

## Environment
- Operating System: Windows 11
- Account Type: Local user account
- Lab Type: Simulated end-user issue

## Scenario
A user reports that they are unable to sign in to their workstation. The account needs to be reviewed, access restored, and the issue documented for IT records.

---

## Step 1 – Create a Local User Account
I created a local user account to simulate a real end-user.

**Steps taken**
1. Opened **Settings**
2. Navigated to **Accounts → Other users**
3. Selected **Add account**
4. Chose **I don’t have this person’s sign-in information**
5. Selected **Add a user without a Microsoft account**
6. Created a local user account with a temporary password

**Result**
- Local user account successfully created
- Account type: Standard user
- Account was able to sign in successfully before the issue was simulated

---

## Step 2 – Simulate the Access Issue
To simulate a real help desk issue, I intentionally disabled the user account.

**Steps taken**
1. Opened **Computer Management**
2. Navigated to **Local Users**
3. Selected the test user account
4. Disabled the account to prevent login

**Result**
- User was unable to sign in
- Windows displayed an account access error

This simulates a common issue seen during onboarding/offboarding or account misconfiguration.

---

## Step 3 – Restore Access / Reset Password
I restored access by re-enabling the account and resetting the password.

**Steps taken**
1. Re-enabled the disabled user account
2. Reset the password to a new temporary password
3. Instructed that the password should be changed at next login

**Result**
- User was able to sign in successfully
- Access fully restored

---

## Step 4 – Permissions Review
I reviewed the user’s permissions to ensure proper access control.

**Checks performed**
- Verified the account did not have unnecessary administrator privileges
- Confirmed the account remained a standard user
- No additional group memberships were required

**Reasoning**
Using the principle of least privilege helps reduce security risk while still allowing the user to perform their job.

---

## What I Learned
- How to create and manage local user accounts in Windows
- How account disabling can cause login failures
- The importance of documenting access changes
- Why least privilege is important in user access management

## Evidence
This lab was performed locally in a Windows 11 environment using built-in account management tools.
