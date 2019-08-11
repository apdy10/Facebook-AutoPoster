# Python script to log in to facebook and post birthday messages to friends on birthdays!!
 
from selenium import webdriver
from selenium.webdriver.support import ui
from selenium.webdriver.common.keys import Keys
import getpass
import time
 
def page_loaded(driver):
	return driver.find_element_by_tag_name("body") != None
 
# Taking inputs from the console
print("Logging Details for Facebook:\n")
input_email_id = raw_input("Enter Username: ")
input_pwd = getpass.getpass()
 
# Opening the web browser
driver = webdriver.Firefox()
driver.get("https://www.facebook.com")
wait = ui.WebDriverWait(driver, 10)
wait.until(page_loaded)
 
# print(driver.page_source)
 
# Finding email and password fields and sending the keys
email = driver.find_element_by_id("email")
email.send_keys(input_email_id)
pwd = driver.find_element_by_id("pass")
pwd.send_keys(input_pwd)
pwd.send_keys(Keys.RETURN)
 
time.sleep(5)
 
driver.get("https://www.facebook.com/events/birthdays")
 
box_count = len(driver.find_elements_by_class_name("innerWrap"))
 
for x in range(0, box_count):
	text_box = driver.find_element_by_tag_name('textarea')
	text_box.send_keys("Happy Birthday!! \n")	
	# The birthday message
	
	time.sleep(5)
 
driver.close()
