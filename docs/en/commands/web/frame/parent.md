# Switch to Parent Frame

Change focus to the parent context (Web context only)
## Example Usage

```java
// Java
driver.switchTo().parentFrame();

```

```python
# Python
self.driver.switch_to.parent()

```

```javascript
// Javascript
// webdriver.io example
driver.frameParent();



// Not supported
```

```ruby
# Ruby
@driver.parent_frame()

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

If the current context is the top level browsing context, the context remains unchanged


## Client Docs

 * [Java](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/WebDriver.TargetLocator.html#parentFrame--) 
 * [Python](http://selenium-python.readthedocs.io/api.html#selenium.webdriver.remote.webdriver.WebDriver.current_url) 
 * [Javascript (WebdriverIO)](http://webdriver.io/api/protocol/frameParent.html) 

 * [Ruby](http://www.rubydoc.info/gems/selenium-webdriver/Selenium/WebDriver/TargetLocator:parent_frame) 
 * [PHP](https://github.com/appium/php-client/) 
 * [C#](https://github.com/appium/appium-dotnet-driver/) 

## Support

### Appium Server

|Platform|Driver|Platform Versions|Appium Version|Driver Version|
|--------|----------------|------|--------------|--------------|
| iOS | [XCUITest](/docs/en/drivers/ios-xcuitest.md) | None | None | None |
|  | [UIAutomation](/docs/en/drivers/ios-uiautomation.md) | None | None | None |
| Android | [UiAutomator2](/docs/en/drivers/android-uiautomator2.md) | None | None | None |
|  | [UiAutomator](/docs/en/drivers/android-uiautomator.md) | None | None | None |
| Mac | [Mac](/docs/en/drivers/mac.md) | None | None | None |
| Windows | [Windows](/docs/en/drivers/windows.md) | None | None | None |

### Appium Clients 

|Language|Support|
|--------|-------|
|[Java](https://github.com/appium/java-client/releases/latest)| None |
|[Python](https://github.com/appium/python-client/releases/latest)| None |
|[Javascript (WebdriverIO)](http://webdriver.io/index.html)| None |
|[Javascript (WD)](https://github.com/admc/wd/releases/latest)| None |
|[Ruby](https://github.com/appium/ruby_lib/releases/latest)| None |
|[PHP](https://github.com/appium/php-client/releases/latest)| None |
|[C#](https://github.com/appium/appium-dotnet-driver/releases/latest)| None |

## HTTP API Specifications

### Endpoint

`GET /wd/hub/session/:session_id/url`

### URL Parameters

|name|description|
|----|-----------|
|session_id|ID of the session to route the command to|

### JSON Parameters

None

### Response

The current URL (string)

## See Also

* [W3C Specification](https://www.w3.org/TR/webdriver/#dfn-switch-to-parent-frame)
* [JSONWP Specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframeparent)