# appium_test !

## CMD !!
**install Java**

**install Node.js**

**install Android Studio**

**appium.io -> install Appium**

> npm i --location=global appium

**appium.io -> install Appium driver uiautomator2**

> appium driver install uiautomator2

!! automationName: UiAutomator2

!! platformNames: ["Android"]

**run localhost**

> appium

## PyCharm
**create project**

### set up venv
**create new virtual environment**
> python -m venv venv
> 
> py -m venv venv
> 
> python3 -m venv venv

**Select virtual environment for use in current project**
<img width="756" height="308" alt="img" src="https://github.com/user-attachments/assets/91c9e5fc-90a1-48ad-b983-a5c2b5b46068" />

<img width="1020" height="676" alt="img_1" src="https://github.com/user-attachments/assets/d72561d4-10bf-411c-8023-e1b5ac6fea06" />

**transfer to virtual environment**
 <img width="822" height="271" alt="img_2" src="https://github.com/user-attachments/assets/f6cf083d-10f2-4c76-a2d3-bf555642b31f" />

if something like that 
<img width="1024" height="423" alt="img_3" src="https://github.com/user-attachments/assets/309f65a7-c447-4519-b890-a46ab77237bd" />

**go to PowerShell as Administrator**

> Set-ExecutionPolicy RemoteSigned
 
> A
 
**Create New Tab again**

## Requirements
**get list of installed tools**
> pip list

**Generate a list of all Python packages currently installed in the active virtual environment (or in the global Python environment) and save the list to the requirements.txt file**
> pip freeze > requirements.txt

**Install all Python packages listed in the file**
> pip install -r requirements.txt



## Usefull utilites
> pip install Appium-Python-Client

> pip install pytest

## Appium inspector
https://github.com/appium/appium-inspector -> Installation -> Releases -> [Appium-Inspector-2025.8.2-win-x64.exe]


----------------------------------------------------test_appium.py-----------------------------------------------------
```
from appium import webdriver
from appium.webdriver.common.appiumby import AppiumBy
from appium.options.android import UiAutomator2Options
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

capabilities_options = UiAutomator2Options().load_capabilities(capabilities)
appium_server_url = 'http://localhost:4723'

@pytest.fixture()
def driver():
    app_driver = webdriver.Remote(appium_server_url, options=capabilities_options)
    yield app_driver
    if app_driver:
        app_driver.quit()

def test_find_battery(driver) -> None:
    el = driver.find_element(by=AppiumBy.XPATH, value='//*[@text="Battery"]')
    el.click()
    sleep(5)
```

## Problems
**If the emulator doesn’t start:**
1. Wipe data
2. Cold boot
3. Clean disk C
4. Install Microsoft Visual C++


## Run
- start appium server
- run android emulator
- run test

