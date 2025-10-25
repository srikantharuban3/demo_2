# Instruction 

- You are a test automation engineer.  
- Execute all test cases listed in the **"Test Suite"** section.  
- Use **Playwright MCP tools** to perform each test step.  
- If any step or verification fails, mark the **entire test case as failed**.  
- After completing one test case, proceed to the next until all are executed.  
- When all test cases are completed, generate a **Test Execution Report** in `.html` format.  
- The report must include all relevant details such as:  
  - Test case ID and description  
  - Steps executed  
  - Pass/Fail status  
  - Error messages or screenshots (if applicable)  
  - Execution timestamp 
  - Add Bar chart
- Release note should should be sent the following emails. 
  - Srikanth.ruban@gmail.com

# Test suite

## TC 001 - Verify that user can register a new customer

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Click on the Register link.
- Fill the registration page. 
- Use unique username and password. 
- user name should be 10 charactors and should be unique.
- submit the form by clicking on the register page. 
- Verify that welcome message with the new username is displayed.

## TC 002 - Verify user login functionality with valid credentials

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Enter valid username in the username field
- Enter valid password in the password field
- Click on the "Log In" button
- Verify that user is successfully logged in and account overview page is displayed
- Verify that "Welcome [username]" message is displayed

## TC 003 - Verify user login with invalid credentials

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Enter invalid username in the username field
- Enter invalid password in the password field
- Click on the "Log In" button
- Verify that appropriate error message is displayed
- Verify that user remains on the login page

## TC 004 - Verify forgot password functionality

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Click on "Forgot login info?" link
- Enter registered username or email
- Verify that password recovery instructions are displayed
- Verify that user can navigate back to login page

## TC 005 - Verify account overview dashboard after login

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Login with valid credentials
- Verify that dashboard displays all user accounts
- Verify that account numbers are displayed
- Verify that account types are shown (checking, savings, etc.)
- Verify that current balances are displayed for each account
- Verify that quick action links are available (transfer funds, bill pay, account history)

## TC 006 - Verify account details view

- Login to ParaBank with valid credentials
- Click on an account number from the dashboard
- Verify that detailed account information is displayed
- Verify account opening date is shown
- Verify account type and balance details
- Verify transaction history is accessible

## TC 007 - Verify internal fund transfer between own accounts

- Login to ParaBank with valid credentials
- Navigate to "Transfer Funds" page
- Select source account (from dropdown)
- Select destination account (from dropdown)
- Enter transfer amount
- Click "Transfer" button
- Verify transfer confirmation screen is displayed
- Verify that transfer is reflected in both accounts
- Verify confirmation message is shown

## TC 008 - Verify fund transfer to another customer's account

- Login to ParaBank with valid credentials
- Navigate to "Transfer Funds" page
- Select source account
- Enter recipient's account number
- Enter transfer amount
- Click "Transfer" button
- Verify transfer confirmation screen
- Verify confirmation notification is displayed

## TC 009 - Verify fund transfer with insufficient balance

- Login to ParaBank with valid credentials
- Navigate to "Transfer Funds" page
- Select source account with low balance
- Enter amount greater than available balance
- Attempt to transfer
- Verify that insufficient funds error message is displayed
- Verify that transfer is not processed

## TC 010 - Verify bill payment functionality

- Login to ParaBank with valid credentials
- Navigate to "Bill Pay" section
- Enter payee information (name, address, account)
- Enter payment amount
- Select account to pay from
- Click "Send Payment" button
- Verify payment confirmation screen
- Verify payment is recorded in transaction history

## TC 011 - Verify transaction history view

- Login to ParaBank with valid credentials
- Navigate to account overview
- Click on "Activity" or transaction history for an account
- Verify that transaction history is displayed
- Verify date, description, amount columns are shown
- Verify balance after each transaction is displayed
- Verify transactions are listed in chronological order

## TC 012 - Verify automatic session timeout

- Login to ParaBank with valid credentials
- Remain inactive for more than 15 minutes
- Attempt to perform any banking operation
- Verify that user is automatically logged out
- Verify that user is redirected to login page with timeout message

## TC 013 - Verify manual logout functionality

- Login to ParaBank with valid credentials
- Click on "Log Out" button/link
- Verify that user is logged out successfully
- Verify that user is redirected to homepage
- Verify that session is terminated (back button should not access secure pages)

## TC 014 - Verify informational pages accessibility

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Click on "About Us" link
- Verify About Us page loads with bank information
- Navigate back and click "Services" link
- Verify Services page displays available services
- Navigate and verify "Products" page
- Navigate and verify "Locations" page
- Navigate and verify "Contact Us" page

## TC 015 - Verify contact us form functionality

- Navigate to "Contact Us" page
- Fill in contact form with valid information
- Enter name, email, phone, and message
- Click "Send" or "Submit" button
- Verify confirmation message is displayed
- Verify form submission success

## TC 016 - Verify responsive design on mobile devices

- Navigate to `https://parabank.parasoft.com/parabank/index.htm`
- Resize browser to mobile viewport (or use mobile device)
- Verify that website layout adapts to mobile screen
- Verify that navigation menu is accessible
- Verify that login form is usable on mobile
- Test key functions (login, navigation) on mobile layout

## TC 017 - Verify password complexity requirements

- Navigate to registration page
- Attempt to register with weak password (e.g., "123")
- Verify that password complexity error is displayed
- Enter password meeting requirements
- Verify that registration can proceed with strong password

## TC 018 - Verify account balance inquiry

- Login to ParaBank with valid credentials
- Navigate to account overview
- Verify current balance is displayed for each account
- Click on account to view detailed balance information
- Verify available balance vs. current balance (if applicable)

## TC 019 - Verify system handles concurrent user sessions

- Open ParaBank in multiple browser tabs/windows
- Login with same credentials in multiple sessions
- Perform banking operations in different sessions
- Verify that system handles concurrent access appropriately
- Verify data consistency across sessions

## TC 020 - Verify error handling for invalid account numbers

- Login to ParaBank with valid credentials
- Navigate to fund transfer
- Enter invalid or non-existent recipient account number
- Attempt to transfer funds
- Verify appropriate error message for invalid account
- Verify that transfer is not processed