from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.chrome.service import Service as ChromeService
import smtplib
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart

# Email configuration (replace with your SMTP server details)
SMTP_SERVER = 'YOUR_SMTP_SERVER'
SMTP_PORT = YOUR_SMTP_PORT  # For example, 25
SENDER_EMAIL = 'YOUR_SENDER_EMAIL'
RECIPIENT_EMAIL = 'YOUR_RECIPIENT_EMAIL'

# Function to send email
def send_email(subject, body):
    msg = MIMEMultipart()
    msg['From'] = SENDER_EMAIL
    msg['To'] = RECIPIENT_EMAIL
    msg['Subject'] = subject
    msg.attach(MIMEText(body, 'plain'))

    try:
        with smtplib.SMTP(SMTP_SERVER, SMTP_PORT) as server:
            server.send_message(msg)
        print("Email sent successfully.")
    except Exception as e:
        print(f"Failed to send email: {e}")

# Function to close the current tab
def close_tab():
    driver.close()  # Close the current tab

# Set up Chrome options
chrome_options = Options()
chrome_options.add_argument('ignore-certificate-errors')
chrome_options.add_experimental_option("detach", True)
chrome_options.binary_location = "path/to/your/chrome.exe"  # Replace with your Chrome binary path
driver = webdriver.Chrome(options=chrome_options, service=ChromeService(executable_path="path/to/your/chromedriver.exe"))

# Navigate to login page
driver.get("https://example.com/login")  # Replace with your target URL that you need to monitor 

# Type username and password
username_locator = driver.find_element(By.ID, "j_username")  #Replace with the correct locator you can use ID or XPATH (Attached Video to help you get the correct locators)
username_locator.send_keys("YOUR_USERNAME")  # Replace with your username
password_locator = driver.find_element(By.ID, "j_password")  #Replace with the correct locator you can use ID or XPATH (Attached Video to help you get the correct locators)
password_locator.send_keys("YOUR_PASSWORD")  # Replace with your password

# Click login button
login_button = driver.find_element(By.XPATH, "//button[@id='loginButton']") #Replace with the correct locator you can use ID or XPATH (Attached Video to help you get the correct locators)
login_button.click()

# Verify new page URL
action_url = driver.current_url

# Check if redirected to the correct URL
if action_url != "https://example.com/dashboard":  # Replace with expected URL
    subject = "Login Failure Notification"
    body = "Unexpected URL is returned. Please note that the login failed."
    send_email(subject, body)
else:
    # Verify welcome message (only if URL is correct)
    welcome_text = driver.find_element(By.XPATH, "//h2[contains(@class, 'dashboard--welcome')]")
    actual_text = welcome_text.text
    assert actual_text == "Welcome [YOUR_NAME]"  # Replace with expected welcome text

# Optionally close the tab after the actions
close_tab()
