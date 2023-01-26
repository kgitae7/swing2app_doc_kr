---
description: 스윙투앱 푸시발송 API
---

# 푸시 API를 이용하여 푸시 발송하기

<mark style="color:blue;">푸시 API 를 이용하여 스윙투앱 푸시 발송하기</mark>

스윙투앱에서는 대시보드에서 발송하는 푸시 메시지를  API 형태로 발송하는 것을 다음과 같이 제공하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.



* API 명세서

{% swagger method="post" path="" baseUrl="https://www.swing2app.com/swapi/push_send" summary="스윙투앱앱으로 푸시를 발송하기 위한 API" %}
{% swagger-description %}
<mark style="color:orange;">

*** 발급이 필요한 앱 아이디, API KEY 는 고객센터에 요청하시면 발급이 가능합니다.**

</mark>
{% endswagger-description %}

{% swagger-parameter in="body" name="app_id" required="true" type="" %}
스윙투앱에서 제공하는 APP_ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="api_user" required="true" type="" %}
스윙투앱 사용자 계정(이메일 주소)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="api_key" required="true" %}
스윙투앱에 발급받은 API KEY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="send_target_list" required="true" %}
발송할 대상 사용자 아이디

단일 발송시 user\_id

다중발송시 “,”로 구분하여 입력

Ex:)  user\_id1,user\_id2

전체 발송시 -1 입력

Ex:) -1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="send_target_type_list" required="true" %}
발송대상 유형 설정항목\
개별 사용자에게 보낼경우 개수만큼 MEMBER 라고 입력 ‘,’로 구분하여

전체에게 발송할 경우 ‘ALL\_TARGET’ 이라고 넣는다.\


\[2명의 특정 사용자에게 보낼경우]

Ex:) MEMBER,MEMBER

\[전체발송의 경우]

Ex:) ALL\_TARGET
{% endswagger-parameter %}

{% swagger-parameter in="body" name="send_type" required="true" %}
발송 유형을 입력 푸시발송일 경우 push 라고 입력
{% endswagger-parameter %}

{% swagger-parameter in="body" name="message_json" required="true" %}
메시지 본문 내용 입력\
\* JSON 형식문자열에 맞게 아래 변수 입력

messageTitle:제목,

messageContent:내용

messageLinkUrl:링크주소

messageImageUrl:이미지 주소

\*링크주소와 이미지 주소가 없을 경우 생략 가능\
입력 예:)

\[제목,내용,링크,이미지를 전송할 경우]

{“messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" , "messageLinkUrl" : "http://m.naver.com" , "messageImageUrl":"http://www.swing2app.com/abc.png"}

\[제목,내용,이미지만 전송할 경우]

{“messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" , "messageImageUrl":"http://www.swing2app.com/abc.png"}

\[제목 내용만 전송할 경우]

{“messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" }
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
    result : true, // message id 
    userCount : 3 , // 발송 사용자 Count
    remainSmsCount 0, 
    isPaymentSms : F
}
```
{% endswagger-response %}
{% endswagger %}

* Code 예제

{% tabs %}
{% tab title="Javascript-jQuery" %}
```javascript
var form = new FormData();
form.append("app_id", "app_id");
form.append("api_user", "UserAccount");
form.append("api_key", "api_key");
form.append("send_target_list", "test");
form.append("send_target_type_list", "MEMBER");
form.append("send_type", "push");
form.append("message_json", "{\"messageTitle\" : \"타이틀 내용\" , \"messageContent\" : \"보내는 내용. 네이버 테스트\" , \"messageLinkUrl\" : \"http://m.naver.com\" , \"messageImageUrl\":\"http://www.swing2app.com/abc.png\"}");

var settings = {
  "url": "https://www.swing2app.com/swapi/push_send",
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
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/push_send")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("api_user", "UserAccount")
  .field("api_key", "api_key")
  .field("send_target_list", "test")
  .field("send_target_type_list", "MEMBER")
  .field("send_type", "push")
  .field("message_json", "{\"messageTitle\" : \"타이틀 내용\" , \"messageContent\" : \"보내는 내용. 네이버 테스트\" , \"messageLinkUrl\" : \"http://m.naver.com\" , \"messageImageUrl\":\"http://www.swing2app.com/abc.png\"}")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/push_send',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','api_user' => 'UserAccount','api_key' => 'api_key','send_target_list' => 'test','send_target_type_list' => 'MEMBER','send_type' => 'push','message_json' => '{"messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" , "messageLinkUrl" : "http://m.naver.com" , "messageImageUrl":"http://www.swing2app.com/abc.png"}'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="ETC" %}
아래의 Postman 링크를 참고하여 각 언어별 사용예제를 참고해보세요



[https://documenter.getpostman.com/view/14364369/2s83zdxSKf#b79b93a1-9f46-4d1c-a961-33afa5bfde3f](https://documenter.getpostman.com/view/14364369/2s83zdxSKf#b79b93a1-9f46-4d1c-a961-33afa5bfde3f)
{% endtab %}
{% endtabs %}

****

<mark style="color:blue;">\[javascript 구현 예시 – 전체발송]</mark>

```javascript
var apiUserId = "help@swing2app.co.kr";
var apiKey = "test_api_key";
var appId = "test_app_id";
var messageJson = '{ "messageTitle" : "제목" , "messageContent" : "내용" , 
"messageLinkUrl" : "http://m.naver.com" , "messageImageUrl" : "http://www.swing2app.com/abc.png" }';
var sendTargetList = '-1';
var sendTargetTypeList = "ALL_TARGET";
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_send",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_target_type_list : sendTargetTypeList,
        send_type : 'push' ,
        message_json : messageJson,
        api_user : apiUserId,
        api_key : apiKey
    },
    success: function (model) {
        console.log("푸시 발송 성공");

    }
});
```

<mark style="color:blue;">\[javascript 구현 예시 – 개별발송]</mark>

```javascript
var apiUserId = "help@swing2app.co.kr";
var apiKey = "test_api_key";
var appId = "test_app_id";
var messageJson = '{ "messageTitle" : "제목" , "messageContent" : "내용"}';
var sendTargetList = 'user_id';
var sendTargetTypeList = "MEMBER";
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_send",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_target_type_list : sendTargetTypeList,
        send_type : 'push' ,
        message_json : messageJson,
        api_user : apiUserId,
        api_key : apiKey
    },
    success: function (model) {
        console.log("푸시 발송 성공");

    }
});
```

