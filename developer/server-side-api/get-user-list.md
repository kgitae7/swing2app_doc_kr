---
description: 스윙투앱 사용자 목록 조회 API
---

# 사용자 목록 가져오기

## 사용자 목록 조회 API (Get User List)

***

<mark style="color:blue;">스윙투앱에서 앱 사용자 목록을 페이징으로 조회하는 API</mark>

스윙투앱에서는 대시보드의 사용자 관리 정보를 API 형태로 조회할 수 있도록 다음과 같이 제공합니다.\
사전에 협의되지 않은 방식의 API 사용, 과도한 빈도의 호출은 제한될 수 있습니다.

<mark style="color:red;">\*해당 API는 유료앱 사용자에게 제공되는 항목입니다.</mark>\
<mark style="color:red;">\*App Id, App Key 정보는 아래 가이드에서 확인 가능합니다.</mark>

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}

* API 명세서

### 사용자 목록 조회 API

<mark style="color:green;">`GET/POST`</mark> `https://www.swing2app.com/swapi/get-user_list`

<mark style="color:orange;">\*APP ID, API KEY 는 API KEY 관리 페이지에서 확인 가능합니다.</mark>

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/service/api_key" %}

**Request Parameters (Body 또는 Query)**

| Name                                             | Type    | Required | Description         |
| ------------------------------------------------ | ------- | -------- | ------------------- |
| app\_id <mark style="color:red;">\*</mark>       | String  | Yes      | 스윙투앱에서 제공하는 APP ID  |
| app\_api\_key <mark style="color:red;">\*</mark> | String  | Yes      | 스윙투앱에 발급받은 API KEY  |
| page <mark style="color:red;">\*</mark>          | Integer | Yes      | 조회할 페이지 번호 (1부터 시작) |
| pageSize <mark style="color:red;">\*</mark>      | Integer | Yes      | 페이지당 항목 수 (최대 1000) |



**Response**

{% tabs %}
{% tab title="200: OK (성공)" %}
```json
{
  "result": true,
  "list": [
    { "userStringId": "아이디_22", "userName": "이름_22", "userId": 1305092 },
    { "userStringId": "아이디_21", "userName": "이름_21", "userId": 1305091 },
    { "userStringId": "아이디_20", "userName": "이름_20", "userId": 1305090 },
    { "userStringId": "아이디_19", "userName": "이름_19", "userId": 1305089 },
    { "userStringId": "아이디_18", "userName": "이름_18", "userId": 1305088 }
  ]
}
```

**필드 설명**

* `result` : 처리 성공 여부 (true/false)
* `list[].userStringId` : 사용자가 로그인에 사용하는 문자열 아이디(외부 노출용 ID)
* `list[].userName` : 사용자 이름
* `list[].userId` : 내부 사용자 고유 식별자(숫자형)
{% endtab %}

{% tab title="200: (실패)" %}
```json
{ "result": false }
```

요청 파라미터 누락, 인증 실패(app\_api\_key/app\_id 불일치), 서버 오류 등에서 실패 응답이 반환됩니다.
{% endtab %}
{% endtabs %}

***

### 사용 예시 (Code Samples)

{% tabs %}
{% tab title="curl (GET)" %}
```bash
curl -G "https://www.swing2app.com/swapi/get-user_list" \
  --data-urlencode "app_id=YOUR_APP_ID" \
  --data-urlencode "app_api_key=YOUR_API_KEY" \
  --data-urlencode "page=1" \
  --data-urlencode "pageSize=50"
```
{% endtab %}

{% tab title="curl (POST, form)" %}
```bash
curl -X POST "https://www.swing2app.com/swapi/get-user_list" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  --data "app_id=YOUR_APP_ID&app_api_key=YOUR_API_KEY&page=1&pageSize=50"
```
{% endtab %}

{% tab title="Javascript-jQuery" %}
```javascript
var form = new FormData();
form.append("app_id", "YOUR_APP_ID");
form.append("app_api_key", "YOUR_API_KEY");
form.append("page", "1");
form.append("pageSize", "50");

var settings = {
  "url": "https://www.swing2app.com/swapi/get-user_list",
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

{% tab title="Java (Unirest)" %}
```java
Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/get-user_list")
  .multiPartContent()
  .field("app_id", "YOUR_APP_ID")
  .field("app_api_key", "YOUR_API_KEY")
  .field("page", "1")
  .field("pageSize", "50")
  .asString();

System.out.println(response.getBody());
```
{% endtab %}

{% tab title="PHP (cURL)" %}
```php
<?php
$curl = curl_init();
curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/get-user_list',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array(
    'app_id' => 'YOUR_APP_ID',
    'app_api_key' => 'YOUR_API_KEY',
    'page' => '1',
    'pageSize' => '50'
  ),
));

$response = curl_exec($curl);
curl_close($curl);
echo $response;
```
{% endtab %}
{% endtabs %}

***

### 페이징 가이드

* `page`: 1부터 시작합니다.
* `pageSize`: 최대 1000까지 허용됩니다. (과도한 값 사용 시 호출 제한 가능)
* 마지막 페이지 이후에는 빈 배열(또는 더 이상 데이터가 없음)이 반환될 수 있습니다.



***

### 주의 및 제한 사항

* API 키와 앱 ID는 외부에 노출되지 않도록 안전하게 보관하세요.
* 과도한 호출은 서비스 품질 유지를 위해 차단될 수 있습니다.
* 시스템 점검/네트워크 장애 상황에서는 일시적으로 호출이 실패할 수 있습니다. 재시도 로직을 권장합니다.
* 응답 스키마는 서비스 개선을 위해 사전 공지 후 변경될 수 있습니다.

***

### 변경 이력 (Changelog)

* **2025-09-17**: 최초 공개 (사용자 목록 조회 API 문서)
