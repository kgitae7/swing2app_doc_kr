---
description: 스윙투앱 푸시발송 API
---

# 푸시 API를 이용하여 푸시 발송하기

***

<mark style="color:blue;">푸시 API 를 이용하여 스윙투앱 푸시 발송하기</mark>

스윙투앱에서는 대시보드에서 발송하는 푸시 메시지를  API 형태로 발송하는 것을 다음과 같이 제공하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

<mark style="color:red;">\*해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.</mark>&#x20;

&#x20;<mark style="color:red;">\*App Id, App Key 정보는 아래 가이드에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



* API 명세서

## 스윙투앱으로 푸시를 발송하기 위한 API

<mark style="color:green;">`POST`</mark> `https://www.swing2app.com/swapi/push_api_send_message`

<mark style="color:orange;">\*APP ID, API KEY 는 API KEY 관리 페이지에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



#### Request Body

| Name                                                       | Type   | Description                                                                                                                                                                                            |
| ---------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| app\_id<mark style="color:red;">\*</mark>                  |        | 스윙투앱에서 제공하는 APP\_ID                                                                                                                                                                                    |
| app\_api\_key<mark style="color:red;">\*</mark>            | String | 스윙투앱에 발급받은 API KEY                                                                                                                                                                                     |
| send\_target\_list<mark style="color:red;">\*</mark>       | String | <p>발송할 대상 사용자 아이디</p><p>(최대 100명 까지 발송가능)</p><p>단일 발송시 user_id</p><p>다중발송시 “,”로 구분하여 입력</p><p>Ex:)  user_id1,user_id2</p><p>전체 발송시 -1 입력</p><p>Ex:) -1</p>                                             |
| send\_target\_type\_list<mark style="color:red;">\*</mark> | String | <p>발송대상 유형 설정항목<br>개별 사용자에게 보낼경우 개수만큼 MEMBER 라고 입력 ‘,’로 구분하여</p><p>전체에게 발송할 경우 ‘ALL_TARGET’ 이라고 넣는다.<br></p><p>[2명의 특정 사용자에게 보낼경우]</p><p>Ex:) MEMBER,MEMBER</p><p>[전체발송의 경우]</p><p>Ex:) ALL_TARGET</p> |
| send\_type<mark style="color:red;">\*</mark>               | String | 발송 유형을 입력 푸시발송일 경우 push 라고 입력                                                                                                                                                                          |
| message\_title<mark style="color:red;">\*</mark>           | String | 푸시 메시지 제목                                                                                                                                                                                              |
| message\_content<mark style="color:red;">\*</mark>         | String | 푸시 메시지 내용                                                                                                                                                                                              |
| message\_image\_url                                        | String | <p>이미지 주소<br>(이미지가 없을 경우 생략가능)</p>                                                                                                                                                                     |
| message\_link\_url                                         | String | <p>링크 주소<br>(링크가 없을 경우 생략가능)</p>                                                                                                                                                                       |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    // Response
    result : true, // 메시지 발송 성공여부
    userCount : 3 , // 발송 사용자 Count
    remainSmsCount 0, 
    isPaymentSms : F
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
form.append("send_target_list", "test");
form.append("send_target_type_list", "MEMBER");
form.append("send_type", "push");
form.append("message_title", "메시지 제목");
form.append("message_content", "메시지 내용");
form.append("message_image_url", "https://www.swing2app.co.kr/assets/images/logo.png");
form.append("message_link_url", "https://www.swing2app.co.kr/");

var settings = {
  "url": "https://www.swing2app.com/swapi/push_api_send_message",
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
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/push_api_send_message")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("app_api_key", "api_key")
  .field("send_target_list", "test")
  .field("send_target_type_list", "MEMBER")
  .field("send_type", "push")
  .field("message_title", "메시지 제목")
  .field("message_content", "메시지 내용")
  .field("message_image_url", "https://www.swing2app.co.kr/assets/images/logo.png")
  .field("message_link_url", "https://www.swing2app.co.kr/")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/push_api_send_message',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','app_api_key' => 'api_key','send_target_list' => 'test','send_target_type_list' => 'MEMBER','send_type' => 'push','message_title' => '메시지 제목','message_content' => '메시지 내용','message_image_url' => 'https://www.swing2app.co.kr/assets/images/logo.png','message_link_url' => 'https://www.swing2app.co.kr/'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="ETC" %}
아래의 Postman 링크를 참고하여 각 언어별 사용예제를 참고해보세요



[https://documenter.getpostman.com/view/14364369/2s83zdxSKf#b8515d97-a411-405e-a633-2fda134970b4](https://documenter.getpostman.com/view/14364369/2s83zdxSKf#b8515d97-a411-405e-a633-2fda134970b4)
{% endtab %}
{% endtabs %}





<mark style="color:blue;">\[javascript 구현 예시 – 전체발송]</mark>

```javascript
var apiKey = "test_api_key";
var appId = "test_app_id";
var sendTargetList = '-1';
var sendTargetTypeList = "ALL_TARGET";
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_api_send_message",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_target_type_list : sendTargetTypeList,
        send_type : 'push' ,
        message_title:'메시지 제목',
        message_content:'메시지 내용',
        message_image_url: 'https://www.swing2app.co.kr/assets/images/logo.png',
        message_link_url: 'https://www.swing2app.co.kr/',
        app_api_key : apiKey
    },
    success: function (model) {
        console.log("푸시 발송 성공");

    }
});
```

<mark style="color:blue;">\[javascript 구현 예시 – 개별발송]</mark>

```javascript
var apiKey = "test_api_key";
var appId = "test_app_id";
var sendTargetList = 'user_id';
var sendTargetTypeList = "MEMBER";
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_api_send_message",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_target_type_list : sendTargetTypeList,
        send_type : 'push' ,
        message_title:'메시지 제목',
        message_content:'메시지 내용',
        message_image_url: 'https://www.swing2app.co.kr/assets/images/logo.png',
        message_link_url: 'https://www.swing2app.co.kr/',
        app_api_key : apiKey
    },
    success: function (model) {
        console.log("푸시 발송 성공");

    }
});
```

