URL and Login Monitoring Script with Selenium
This project is a Python script that monitors the availability of public URLs and verifies the login functionality on a target website. Using Selenium WebDriver, it automatically checks if URLs are reachable and validates login by simulating user input. In case of login failures, an email notification is sent.

Features
URL Monitoring: Periodically checks if specified URLs are accessible.
Login Verification: Simulates a login process to ensure authentication is working.
Automated Email Notification: Sends an email alert if login verification fails.
Prerequisites
Python (version 3.6 or higher)
Selenium WebDriver: Install via pip:
pip install selenium


ChromeDriver: Download the version compatible with your Chrome browser from ChromeDriver.
Setup
Clone this repository to your local machine.
Replace placeholder values in the script with your own configuration details as explained below.
Configuration
In the script.py file:

SMTP_SERVER: Replace 'YOUR_SMTP_SERVER' with your SMTP server address.
SMTP_PORT: Replace YOUR_SMTP_PORT with the port number, e.g., 25.
SENDER_EMAIL and RECIPIENT_EMAIL: Replace with the sender and recipient email addresses.
chrome_options.binary_location: Set the path to your Chrome binary.
webdriver.Chrome service: Replace the path to your chromedriver.exe.
Login Details:
Update the target login URL and expected redirect URL.
Update placeholders for USERNAME and PASSWORD.
Usage
To run the script:
python script.py

Finding Element XPaths
To get the XPaths of elements (e.g., username, password fields, and buttons), follow this XPath tutorial on YouTube for step-by-step guidance.
Also the below link is the official selenium documentation for locators:
https://www.selenium.dev/documentation/webdriver/elements/locators/
