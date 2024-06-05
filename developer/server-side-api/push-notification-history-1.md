---
description: 스윙투앱 푸시알림 목록에서 읽지 않은 메시지 Count 가져오기 API
---

# 푸시알림 읽지 않은 메시지 Count

스윙투앱에서는 발송한 목록에 읽지 않은 메시지에 대한 Count 를 가져오는 API 를 제공하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

<mark style="color:red;">\*해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.</mark>&#x20;

<mark style="color:red;">\*App Id, App Key 정보는 아래 가이드에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



* API 명세서

## 푸시알림 읽지 않은 메시지 Count 를 받기위한 API

<mark style="color:green;">`POST`</mark> `https://www.swing2app.com/swapi/push_unread_count`

<mark style="color:orange;">\*APP ID, API KEY 는 API KEY 관리 페이지에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



#### Request Body

| Name                                            | Type   | Description                                 |
| ----------------------------------------------- | ------ | ------------------------------------------- |
| app\_id<mark style="color:red;">\*</mark>       | String | 스윙투앱에서 제공하는 APP\_ID                         |
| app\_api\_key<mark style="color:red;">\*</mark> | String | 스윙투앱에 발급받은 API KEY                          |
| platform<mark style="color:red;">\*</mark>      | String | <p>대상플랫폼<br>("AND" or "IOS")</p>            |
| user\_id<mark style="color:red;">\*</mark>      | String | 푸시 알람 수신 대상자를 지정하는 회원 아이디 ( 예: test\_user ) |



{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    "result": true,
    "pushUnreadCount": 0
}
```
{% endtab %}
{% endtabs %}

* Code 예제

{% tabs %}
{% tab title="Javascript-jQuery" %}
```javascript
var form = new FormData();
form.append("app_id", "app_id");
form.append("app_api_key", "api_key");
form.append("platform", "android");
form.append("user_id", "tets");

var settings = {
  "url": "https://www.swing2app.com/swapi/push_unread_count",
  "method": "POST",
  "timeout": 0,
  "processData": false,
  "mimeType": "multipart/form-data",
  "contentType": false,
  "data": form
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Java" %}
```java
Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/push_unread_count")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("app_api_key", "api_key")
  .field("platform", "AND")
  .field("user_id", "test_user")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/push_unread_count',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','app_api_key' => 'api_key','user_id' => 'test_user','platform' => 'AND'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="ETC" %}
아래의 Postman 링크를 참고하여 각 언어별 사용예제를 참고해보세요

[https://documenter.getpostman.com/view/14364369/2s83zdxSKf#a22a9eb9-5e53-45f4-9bc3-4f3a4c0aa55b](https://documenter.getpostman.com/view/14364369/2s83zdxSKf#a22a9eb9-5e53-45f4-9bc3-4f3a4c0aa55b)
{% endtab %}
{% endtabs %}
