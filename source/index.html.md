---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - swift
  - objective_c

toc_footers:
  - <a href='http://pager.com'>Sign Up for a Developer Key</a>

search: true
---

# Introduction

# Installation

Welcome to Pager's iOS SDK. This library will help you use our telemedicine systems with ease.

**The Pager iOS SDK requires Xcode 9+ and a Base SDK of iOS 10+**. It permits a Deployment Target of iOS 10.0 or higher.

We recommend using either [CocoaPods](https://github.com/CocoaPods/CocoaPods) to integrate the Pager SDK with your project.

### CocoaPods
Add the dependency into your podfile

```ruby
source 'git@github.com:pagerinc/ios-specs-public.git'
source 'https://github.com/CocoaPods/Specs.git'

inhibit_all_warnings!

platform :ios, '10.0'

target 'YourTarget' do
  use_frameworks!

  pod 'PagerKit'
end

```

## Framework
Download the PagerKit.framework,
add it to embedded binaries and linked frameworks and libraries in the general tab of your app target.

![linked framework](/images/linked_frameworks.png)

Download Twilio Library and add it to the embedded binaries and linked frameworks in the general tab of your app target or install it via cocoapods `pod 'TwilioVideo'`

<aside class="notice">
The Consumer iOS SDK is built as a universal binary in order to support all potential architectures but before submitting to the App Store, you will need to remove any architectures that are not supported by the App Store. You can resolve this issue by doing either of the following:
Add a build phase script that strips the unsupported architectures (x86_64, i386) from the framework.
Use the shell script <code>trim.sh</code> that’s included in the SDK software distribution package along with the instructions documented under the App Store Deployment section of the Consumer iOS SDK guide to remove the unsupported architectures.
</aside>


# Setup

## Config


```objective_c
#import <PagerKit/PagerKit.h>

PKITClientConfig *config = [[PKITClientConfig alloc] init];
config.appKey = "<YOUR_CLIENT_ID>"
config.userToken = "<USER_TOKEN>"
```

```swift
import PagerKit

let config = PKITClientConfig()
config.appKey = "<YOUR_CLIENT_ID>"
config.userToken = "<USER_TOKEN>"
```

## Theme

```objective_c
#import <PagerKit/PagerKit.h>

PKITTheme *theme = [[PKITTheme alloc] init];
theme.primaryColor = UIColor.redColor;
config.theme = theme;
```

```swift
import PagerKit

let theme = PKITTheme()
theme.primaryColor = UIColor.red
config.theme = theme
```

## Notifications

# Session

# Encounter Context

## Fetch

```objective_c
[PKITClient encounterContextForConsumerSession:self.consumerSession completion:^(PKITEncounterContext *context, NSError *error) {
  if (!error) {
    [context addListener:self];
  }
}];
```

```swift
PKITClient.encounterContext(for: session, completion: { (context, error) in
  if let context = context, error == nil {
    context.addListener(self)
  }
})
```

## Create

```objective_c
```

```swift
```

# Provided Services

# Controllers

## Encounter
## Payments
## Insurances
## Promotions
## Appointments
## Encounter History

<!-- ---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
 -->
