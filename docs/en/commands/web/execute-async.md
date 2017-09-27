# Execute Async Script

Inject a snippet of JavaScript into the page for execution in the context of the currently selected frame (Web context only)
## Example Usage

```java
// Java
((JavascriptExecutor) driver).executeAsyncScript("window.setTimeout(arguments[arguments.length - 1], 500);");

```

```python
# Python
self.driver.execute_async_script(‘document.title’)

```

```javascript
// Javascript
// webdriver.io example
browser.timeoutsAsyncScript(5000);
var result = browser.executeAsync(function(a, b, c, d, done) {
    // browser context - you may access neither client nor console
    setTimeout(function() {
        done(a + b + c + d);
    }, 3000);
}, 1, 2, 3, 4)

// node.js context - client and console are available
console.log(result.value); // outputs: 10



// wd example
await driver.safeExecuteAsync('document.title');

```

```ruby
# Ruby
@driver.execute_async_script("document.title")

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

The executed script is assumed to be asynchronous and must signal that is done by invoking the provided callback, which is always provided as the final argument to the function. The value to this callback will be returned to the client.

Asynchronous script commands may not span page loads. If an unload event is fired while waiting for a script result, an error should be returned to the client.

The script argument defines the script to execute in teh form of a function body. The function will be invoked with the provided args array and the values may be accessed via the arguments object in the order specified. The final argument will always be a callback function that must be invoked to signal that the script has finished.

Arguments may be any JSON-primitive, array, or JSON object. JSON objects that define a WebElement reference will be converted to the corresponding DOM element. Likewise, any WebElements in the script result will be returned to the client as WebElement JSON objects.


## Client Docs

 * [Java](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/remote/RemoteWebDriver.html#executeAsyncScript-java.lang.String-java.lang.Object...-) 
 * [Python](http://selenium-python.readthedocs.io/api.html#selenium.webdriver.remote.webdriver.WebDriver.execute_async_script) 
 * [Javascript (WebdriverIO)](http://webdriver.io/api/protocol/executeAsync.html) 
 * [Javascript (WD)](https://github.com/admc/wd/blob/master/lib/commands.js#L182) 
 * [Ruby](http://www.rubydoc.info/gems/selenium-webdriver/Selenium/WebDriver/Driver:execute_async_script) 
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

`GET /wd/hub/session/:session_id/execute_async`

### URL Parameters

|name|description|
|----|-----------|
|session_id|ID of the session to route the command to|

### JSON Parameters

|name|type|description|
|----|-----------|
| script | string | The script to execute |
| args | array | The script arguments |

### Response

The script result (any)

## See Also

* [W3C Specification](https://www.w3.org/TR/webdriver/#dfn-execute-async-script)
* [JSONWP Specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute_async)