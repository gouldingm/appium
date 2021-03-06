# Create New Session

Create a new session
## Example Usage

```java
// Java
DesiredCapabilities desiredCapabilities = new DesiredCapabilities();
desiredCapabilities.setCapability(MobileCapabilityType.PLATFORM_VERSION, "10.3");
desiredCapabilities.setCapability(MobileCapabilityType.DEVICE_NAME, "iPhone Simulator");
desiredCapabilities.setCapability(MobileCapabilityType.AUTOMATION_NAME, "XCUITest");
desiredCapabilities.setCapability(MobileCapabilityType.APP, "/path/to/ios/app.zip");

URL url = new URL("http://127.0.0.1:4723/wd/hub");

IOSDriver driver = new IOSDriver(url, desiredCapabilities);
String sessionId = driver.getSessionId().toString();

```

```python
# Python
desired_caps = desired_caps = {
  'platformName': 'Android',
  'platformVersion': '7.0',
  'deviceName': 'Android Emulator',
  'automationName': 'UiAutomator2',
  'app': PATH('/path/to/app')
}
self.driver = webdriver.Remote('http://127.0.0.1:4723/wd/hub', desired_caps)

```

```javascript
// Javascript
// webdriver.io example
let options = { desiredCapabilities: { 
  platformName: 'Android',
  platformVersion: '7.0',
  automationName: 'UiAutomator2',
  app: path.resolve('path', 'to', 'app.apk')
}};
let client = webdriverio.remote(options);



// wd example
let driver = await wd.promiseChainRemote({
  host: '127.0.0.1',
  port: 4723
});
let desiredCaps = {
  platformName: 'Android',
  platformVersion: '7.0',
  deviceName: 'Android Emulator',
  app: path.resolve('path', 'to', 'app.apk')
};
await driver.init(desiredCaps);

```

```ruby
# Ruby
APP_PATH = '../../path/to/app.app'

desired_caps = {
  caps: {
    platformName:  'iOS',
    platformVersion: '10.2',
    deviceName:    'iPhone 6',
    app:           APP_PATH,
    automationName: "XCUITest"
  }
}

Appium::Driver.new(desired_caps).start_driver

```

```php
# PHP
// TODO PHP sample

```

```csharp
// C#
// TODO C# sample

```


## Description

The server should attempt to create a session that most closely matches the desired and required capabilities. 

* [JSONWP Spec](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1) Required capabilities have higher priority than desired capabilities and must be set for the session to be created
* [W3C Spec](https://www.w3.org/TR/webdriver/#dfn-new-session) capabilities.alwaysMatch must be set for session to be created; capabilities.firstMatch must match at least one (the first one to match will be used)


## Support

### Appium Server

|Platform|Driver|Platform Versions|Appium Version|Driver Version|
|--------|----------------|------|--------------|--------------|
| iOS | [XCUITest](/docs/en/drivers/ios-xcuitest.md) | 9.3+ | 1.6.0+ | All |
|  | [UIAutomation](/docs/en/drivers/ios-uiautomation.md) | 8.0 to 9.3 | All | All |
| Android | [UiAutomator2](/docs/en/drivers/android-uiautomator2.md) | ?+ | 1.6.0+ | All |
|  | [UiAutomator](/docs/en/drivers/android-uiautomator.md) | 4.2+ | All | All |
| Mac | [Mac](/docs/en/drivers/mac.md) | ?+ | 1.6.4+ | All |
| Windows | [Windows](/docs/en/drivers/windows.md) | 10+ | 1.6.0+ | All |

### Appium Clients

|Language|Support|Documentation|
|--------|-------|-------------|
|[Java](https://github.com/appium/java-client/releases/latest)| All |  [seleniumhq.github.io](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/remote/server/DefaultSession.html#createSession-org.openqa.selenium.remote.server.DriverFactory-org.openqa.selenium.remote.server.Clock-org.openqa.selenium.remote.SessionId-org.openqa.selenium.Capabilities-)  |
|[Python](https://github.com/appium/python-client/releases/latest)| All |  [selenium-python.readthedocs.io](http://selenium-python.readthedocs.io/api.html#selenium.webdriver.remote.webelement.WebElement.clear)  |
|[Javascript (WebdriverIO)](http://webdriver.io/index.html)| All |  [webdriver.io](http://webdriver.io/api/action/clearElement.html)  |
|[Javascript (WD)](https://github.com/admc/wd/releases/latest)| All |  [github.com](https://github.com/admc/wd/blob/master/lib/commands.js#L1780)  |
|[Ruby](https://github.com/appium/ruby_lib/releases/latest)| All |  [www.rubydoc.info](http://www.rubydoc.info/gems/selenium-webdriver/Selenium/WebDriver/Element:clear)  |
|[PHP](https://github.com/appium/php-client/releases/latest)| All |  [github.com](https://github.com/appium/php-client/)  |
|[C#](https://github.com/appium/appium-dotnet-driver/releases/latest)| All |  [github.com](https://github.com/appium/appium-dotnet-driver/)  |

## HTTP API Specifications

### Endpoint

`POST /session`

### URL Parameters

None

### JSON Parameters

|name|type|description|
|----|----|-----------|
| desiredCapabilities | `object` | ([JSONWP specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)) Object describing session's [desired capabilities](/docs/en/writing-running-appium/caps.md) |
| requiredCapabilities | `object` | ([JSONWP specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)) Object describing session's required capabilities that must be applied by remote end |
| capabilities | `object` | ([W3C specification])(https://www.w3.org/TR/webdriver/#dfn-new-session) object containing 'alwaysMatch' and 'firstMatch' properties |
| capabilities.alwaysMatch | `object` | The [desired capabilities](/docs/en/writing-running-appium/caps.md) that the remote end must match |
| capabilities.firstMatch | `array<object>` | List of capabilities that the remote end tries to match. Matches the first in the list |

### Response

An object describing the session's capabilities (`object`)

## See Also

* [W3C Specification](https://www.w3.org/TR/webdriver/#dfn-new-session)
* [JSONWP Specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)
