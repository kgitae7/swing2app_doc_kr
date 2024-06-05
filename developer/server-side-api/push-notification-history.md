---
description: 스윙투앱 푸시알림 목록 가져오기 API
---

# 푸시알림 목록 가져오기

<mark style="color:blue;">푸시알림 목록 API 를 이용하여 푸시알림 목록을 가져오기</mark>

스윙투앱에서는 발송한 목록에 히스토리를 API 형태로 제공하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

<mark style="color:red;">\*해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.</mark>&#x20;

<mark style="color:red;">\*App Id, App Key 정보는 아래 가이드에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



* API 명세서

## 푸시 알림 목록을 받기위한 API

<mark style="color:green;">`POST`</mark> `https://www.swing2app.com/swapi/push_notification_history`

<mark style="color:orange;">\*APP ID, API KEY 는 API KEY 관리 페이지에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



#### Request Body

| Name                                            | Type   | Description                                                                                                 |
| ----------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------- |
| app\_id<mark style="color:red;">\*</mark>       |        | 스윙투앱에서 제공하는 APP\_ID                                                                                         |
| app\_api\_key<mark style="color:red;">\*</mark> | String | 스윙투앱에 발급받은 API KEY                                                                                          |
| page<mark style="color:red;">\*</mark>          | String | 데이터 페이지 번호                                                                                                  |
| pageSize<mark style="color:red;">\*</mark>      | String | 데이터 페이지 사이즈( 최대 : 100 )                                                                                     |
| user\_id<mark style="color:red;">\*</mark>      | String | 푸시 알람 수신 대상자를 지정하는 회원 아이디 ( 예: test\_user )                                                                 |
| platform                                        | String | 플랫폼 지정 예: AND , IOS 모두 포함할 경우 공란 또는 생략가능                                                                    |
| offset\_datetime                                | String | 특정 날짜 시점 이후의 데이터를 원할 경우 날짜를 입력 날짜 형식 : YYYY-MM-DD hh:mm 예:) 2024-03-01 10:00 날짜 지정을 원하지 않을 경우 해당 파라미터 생략 가능 |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    "result": true,
    "pushList": [
        {
            "id" : 141512,
            "read_datetime" : 1709614395000, 
            "message_subject": "제목",
            "message_content": "내용",
            "regi_datetime": 1709614395000
        },
        {
            "id" : 141513,
            "read_datetime" : 1709614395000,
            "message_subject": "title",
            "message_content": "content",
            "regi_datetime": 1709520271000
        }
    ]
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
form.append("page", "1");
form.append("pageSize", "10");
form.append("user_id", "test_user");
form.append("platform", "AND");
form.append("offset_datetime", "2024-03-01 10:00");

var settings = {
  "url": "https://www.swing2app.com/swapi/push_notification_history",
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
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/push_notification_history")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("app_api_key", "api_key")
  .field("page", "1")
  .field("pageSize", "10")
  .field("user_id", "test_user")
  .field("platform", "AND")
  .field("offset_datetime", "2024-03-01 10:00")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/push_notification_history',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','app_api_key' => 'api_key','page' => '1','pageSize' => '10','user_id' => 'test_user','platform' => 'AND','offset_datetime' => '2024-03-01 10:00'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="ETC" %}
아래의 Postman 링크를 참고하여 각 언어별 사용예제를 참고해보세요

[https://documenter.getpostman.com/view/14364369/2s83zdxSKf#80c09fc0-6973-4827-9a4c-9a6c527c799b](https://documenter.getpostman.com/view/14364369/2s83zdxSKf#80c09fc0-6973-4827-9a4c-9a6c527c799b)
{% endtab %}
{% endtabs %}
