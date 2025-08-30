# appium_test

##CMD
install Java
install Node.js
install Android Studio

appium.io -> install Appium
>> npm i --location=global appium

appium.io -> install Appium driver uiautomator2
>> appium driver install uiautomator2
!!!- automationName: UiAutomator2
!!- platformNames: ["Android"]

run localhost
>> appium

##PyCharm
create project 
set up venv

>> pip install Appium-Python-Client
>> pip install pytest

----------------------------------------------------test_appium.py-----------------------------------------------------
from appium import webdriver
from appium.webdriver.common.appiumby import AppiumBy
from appium.options.android UiAutomator2Options
import pytest
from time import sleep

capabilities = dict(
    platformName='Android',
    automationName='uiautomator2',
    deviceName='Android',
    appPackage='com.android.settings',
    appActivity='.Settings',
    language='en',
    locale='US'
)

capabilities_options = UiAtomator2Options().load.capabilities(capabilities)
appium_server_url = 'http://localhost:4723'

@pytest.fixture()
def driver():
  app_driver = webdriver.Remote(appium_server_url, options=capabilities_options)
  yield app_driver
  if driver:
    driver.quit()

def test_find_battery(driver) -> None:
    el = driver.find_element(by=AppiumBy.XPATH, value='//*[@text="Battery"]')
    el.click()
    sleep(5)

----------------------------------------------------test_appium.py-----------------------------------------------------
