                  ** Automated Testing of E-commerce Web Application(SAUCE DEMO) **
		
This project automates the testing of the web application (https://www.saucedemo.com/) by simulating user actions and validating its core functionalities. The key modules covered include logging in with different user roles, navigating the product catalog, adding items to the cart, and completing the purchase flow.It ensures the reliability of critical components through both positive and negative test scenarios.

The test scripts are developed using Selenium with Python and Pytest, following the Hybrid framework [Page Object Model (POM),Data Driven,Keyword Driven framework] and adhering to Object-Oriented Programming (OOP) principles. The test data is externalized (CSV) using Data Driven framework,Keyword Driven Testing framework and common configurations are handled in config.py.The valid and invalid login data are externalized (CSV) using Data Driven framework.Keywords are stored as CSV file which access the methods in keywords.py file using Keyword Driven Testing framework.The suite includes 10 detailed test cases focused on verifying page behavior, accessibility of essential elements, navigation flows, and login/logout processes.


**Project Architecture :**

**Capstone/**
│
├── **Data/**
│   ├── __init__.py
│   ├── invalid_login_data.csv
│   ├── keywords_05_select_products.csv
│   ├── keywords_06_add_to_cart.csv
│   ├── keywords_06_invalid_cart_count.csv
│   ├── keywords_07_validate_cart_items.csv
│   ├── keywords_08_complete_checkout.csv
│   ├── keywords_08_error_checkout.csv
│   ├── login_data.csv
│
├── **Pages/**
│   ├── __init__.py
│   ├── base_page.py
│   ├── cart_page.py
│   ├── checkout_page.py
│   ├── inventory_page.py
│   ├── login_page.py
│
├── **Screenshots/**
│   ├──screenshot.png
│
├── **Tests/**
│   ├── __init__.py
│   ├── conftest.py
│   ├── keywords.py
│   ├── test_01_validate_login.py
│   ├── test_02_invalid_credentials.py
│   ├── test_03_validate_logout.py
│   ├── test_04_check_cart_icon.py
│   ├── test_05_select_items.py
│   ├── test_06_add_to_cart.py
│   ├── test_06_invalid_cart_count.py
│   ├── test_07_validate_cart_items.py
│   ├── test_08_complete_checkout.py
│   ├── test_08_invalid_checkout.py
│   ├── test_09_sort_options.py
│   ├── test_10_reset_app_state.py
│
├── **Utils/**
│   ├── __init__.py
│   ├── config.py
│
├── requirements.txt
├── README.md


**Tools & Technologies:**
*     Selenium WebDriver
*     Python 
*     Pytest
*     OOPS
*     Page Object Model (POM)
*     Data Driven framework
*     Keyword Driven framework
*     Test Data(CSV file)
*     Explicit Waits
*     Exception Handling
*     Pytest HTML Reports



**Test Suite :**

Test Case 1: Validates login functionality using multiple sets of credentials using external CSV file

	* Positive case: Properly enters orangehrm login page and enters valid data and clicks logout
	* Negative case: Enters orangehrm login page and enters invalid data and displays error message
 
Test Case 2: Verify that the home URL is accessible

	* Positive case: Validates proper navigation to (https://opensource-demo.orangehrmlive.com) and asserts current URL
	* Negative case: Invalid URL navigation and displays error message

Test Case 3: Validate presence of login fields

	* Locates Username and Password else throws NoSuchElementException
	* Assert Username and Password is visible and interactable

Test Case 4: Checks visibility and clickability of main menu items after login in dashboard page[Admin, PIM, Leave, Time, Recruitment, My Info, Performance, Dashboard]

	* Positive case: Validate menu items after login stored as dictionary are visible and interactable 
	* Negative case: Invalid access to menu items throws error message

Test Case 5:  Creating a new user and validate login using new user credentials

	* Positive case: Login as Admin and navigate to Admin menu and creates new user with valid details[User_role,Status,Employee_name, username, password, confirmpassword]
	* After new user creation,clicks logout and re-enters with new user credentials.
    * Negative case:Creates new user with invalid details like Employee name doesn't start with numbers.Displays error message.Also existing user cannot be created.
 
Test Case 6: Validate presence of the newly created user in the admin user list

	* Positive case: Navigates to Admin menu and validates new user is available in user list
	* Negative case: Navigates to Admin menu and validates not created user is available in user list

Test Case 7: Checks "Forgot Password" link functionality

	* Enters Login page and clicks "Forgot Password" link. 
	* Navigates to Forgot Password and enters username and reset link is sent to mail and displays message

Test Case 8: Validate the presence of menu items under “My Info”[Personal Details,Contact Details,Emergency Contacts,Job,Salary,Qualification,Memberships..]

	* Positive case: Validate menu items under “My Info” stored as dictionary are visible and interactable 
	* Negative case: Invalid access to menu items throws error message

Test Case 9: Assign leave to an employee and verify assignment on Leave List

	* Login as Admin and navigates to Leave menu and add entitlements(Employee_name,Leave_Type, Entitled_Days)
    * Assign leave to an employee by providing (Employee_name,Leave_Type,From_Date,To_Date) details
    * After successful leave assignment check leave is scheduled on the leave list

Test Case 10: Initiate a claim request and check the assigned claim on Claim list

	* Login as an Employee with new user credentials. Navigate to Claim menu.
	* Submit the claim (Event_Type,Currency_Type) and add expenses(Event_Type, Claim_Date, Claim_Amount)
	* After successful claim submission check claim of an employee is submitted on the claim list



**Instructions:**

1.Ensure Selenium,Python and any Browser(Chrome,Firefox,Edge) installed in your system. 

2.To create a virtual environment,

	>python -m venv venv
 
	>source venv/bin/activate(macOS)
 
	>venv\scripts\activate(Windows)

3.To install the dependencies,

	>pip install -r requirements.txt

4.To execute all the test files,

	>pytest -v -s Tests/

	>pytest pytest -v -s Tests/test_01_validate_login.py(for any specific file)

	>pytest pytest -v -s Tests/test_01_validate_login.py::test_validate_login(for specific method in a test file)



**To Generate HTML Report:**

To install pytest–html package

	>pip install pytest–html

To execute all the test files and generate html report,

	>pytest -v -s Tests/   --html=reports.html    --self-contained-html

To execute single file and generate html report,

	>pytest -v -s Tests/test_01_validate_login.py   --html=case01_report.html   --self-contained-html


**Screen Recording**:https://drive.google.com/file/d/1OzZ3XA--tmqTX2rZV14XwhWyQ-VXCugB/view?usp=sharing














