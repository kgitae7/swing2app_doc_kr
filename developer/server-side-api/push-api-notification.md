---
description: 스윙투앱 푸시발송 API
---

# 푸시 API를 이용하여 푸시 발송하기

<mark style="color:blue;">푸시 API 를 이용하여 스윙투앱 푸시 발송하기</mark>

스윙투앱에서는 대시보드에서 발송하는 푸시 메시지를  API 형태로 발송하는 것을 다음과 같이 제공하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

<mark style="color:red;">\*해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.</mark>&#x20;

<mark style="color:red;">이용권 구매 후 당사 고객센터로 필요한 정보를 요청주시면 App Id, App Key 등의 정보를 보내드립니다.</mark>&#x20;



* API 명세서

## 스윙투앱으로 푸시를 발송하기 위한 API

<mark style="color:green;">`POST`</mark> `https://www.swing2app.com/swapi/push_send`

<mark style="color:orange;">**\* 발급이 필요한 앱 아이디, API KEY 는 고객센터에 요청하시면 발급이 가능합니다.**</mark>

#### Request Body

| Name                                                       | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| app\_id<mark style="color:red;">\*</mark>                  |        | 스윙투앱에서 제공하는 APP\_ID                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| api\_user<mark style="color:red;">\*</mark>                |        | 스윙투앱 사용자 계정(이메일 주소)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| api\_key<mark style="color:red;">\*</mark>                 | String | 스윙투앱에 발급받은 API KEY                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| send\_target\_list<mark style="color:red;">\*</mark>       | String | <p>발송할 대상 사용자 아이디</p><p>단일 발송시 user_id</p><p>다중발송시 “,”로 구분하여 입력</p><p>Ex:)  user_id1,user_id2</p><p>전체 발송시 -1 입력</p><p>Ex:) -1</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| send\_target\_type\_list<mark style="color:red;">\*</mark> | String | <p>발송대상 유형 설정항목<br>개별 사용자에게 보낼경우 개수만큼 MEMBER 라고 입력 ‘,’로 구분하여</p><p>전체에게 발송할 경우 ‘ALL_TARGET’ 이라고 넣는다.<br></p><p>[2명의 특정 사용자에게 보낼경우]</p><p>Ex:) MEMBER,MEMBER</p><p>[전체발송의 경우]</p><p>Ex:) ALL_TARGET</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| send\_type<mark style="color:red;">\*</mark>               | String | 발송 유형을 입력 푸시발송일 경우 push 라고 입력                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| message\_json<mark style="color:red;">\*</mark>            | String | <p>메시지 본문 내용 입력<br>* JSON 형식문자열에 맞게 아래 변수 입력</p><p>messageTitle:제목,</p><p>messageContent:내용</p><p>messageLinkUrl:링크주소</p><p>messageImageUrl:이미지 주소</p><p>*링크주소와 이미지 주소가 없을 경우 생략 가능<br>입력 예:)</p><p></p><p>[제목,내용,링크,이미지를 전송할 경우]</p><p>{"messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" , "messageLinkUrl" : "http://m.naver.com" , "messageImageUrl":"http://www.swing2app.com/abc.png"} </p><p></p><p>[제목,내용,이미지만 전송할 경우] </p><p>{"messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" , "messageImageUrl":"http://www.swing2app.com/abc.png"} </p><p></p><p>[제목 내용만 전송할 경우] </p><p>{"messageTitle" : "타이틀 내용" , "messageContent" : "보내는 내용. 네이버 테스트" }</p> |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    // Response
    result : true, // message id 
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

