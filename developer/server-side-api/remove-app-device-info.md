---
description: 스윙투앱 푸시발송 기기정보 삭제하기
---

# 푸시기기 삭제하기

***

<mark style="color:blue;">API 를 이용하여 기기정보 삭제하기</mark>

스윙투앱에서는 관리하는 푸시 기기정보를 삭제하는 API를 다음과 같은 형태로 제공하고 하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

<mark style="color:red;">\*해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.</mark>&#x20;

&#x20;<mark style="color:red;">\*App Id, App Key 정보는 아래 가이드에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}



* API 명세서

## &#x20;푸시기기 삭제하기 API



<mark style="color:green;">`POST`</mark> `https://www.swing2app.com/swapi/remove_app_user_device_info`

<mark style="color:orange;">\*APP ID, API KEY 는 API KEY 관리 페이지에서 확인 가능합니다.</mark>&#x20;

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}

#### Request Body

| Name                                            | Type   | Description                                                                                |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------------ |
| app\_id<mark style="color:red;">\*</mark>       | String | 스윙투앱에서 제공하는 APP\_ID                                                                        |
| app\_api\_key<mark style="color:red;">\*</mark> | String | 스윙투앱에 발급받은 API KEY                                                                         |
| search\_val<mark style="color:red;">\*</mark>   | String | <p>아래의 3개 값 중 일치하는 값을 삭제(조회값)</p><p>-device token <br>-uuid<br>-user_string_id(사용자아이디)</p> |



{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    // Response
    result : 1, // 삭제한 회원숫자
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
form.append("search_val", "조회값");

var settings = {
  "url": "https://www.swing2app.com/swapi/remove_app_user_device_info",
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
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/delete_app_user")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("app_api_key", "api_key")
  .field("search_val", "사용자아이디")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/delete_app_user',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','app_api_key' => 'api_key','search_val' => '사용자 아이디'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="ETC" %}
아래의 Postman 링크를 참고하여 각 언어별 사용예제를 참고해보세요



[https://documenter.getpostman.com/view/14364369/2s83zdxSKf#c0e5dca1-d004-4c85-97e3-65a9ec1701de](https://documenter.getpostman.com/view/14364369/2s83zdxSKf#c0e5dca1-d004-4c85-97e3-65a9ec1701de)
{% endtab %}
{% endtabs %}



<mark style="color:blue;">\[javascript 구현 예시 – 기기삭제]</mark>

```javascript
var apiKey = "test_api_key";
var appId = "test_app_id";
var searchVal = '사용자아이디';
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/remove_app_user_device_info",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        user_string_id : userStringId,
        search_val : searchVal
    },
    success: function (model) {
        if( model.result > 0 )
        {
            console.log("회원삭제 성공");
        }        
    }
});
```
