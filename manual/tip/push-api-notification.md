# 푸시 API를 이용하여 푸시 발송하기

<mark style="color:blue;">푸시 API 를 이용하여 스윙투앱 푸시 발송하기</mark>

스윙투앱에서는 대시보드에서 발송하는 푸시 메시지를  API 형태로 발송하는 것을 다음과 같이 제공하고 있습니다.

사전에 협의되지 않은 방식의 API 사용과 , 무분별한 대량발송의 경우 사용에 제한을 받을 수 있습니다.

해당 API 는 유료앱 사용자에게 제공되는 항목 입니다.



**1. API 명세서**

| <mark style="color:blue;">API 주소</mark>      | https://www.swing2app.co.kr/swapi/push\_send |
| -------------------------------------------- | -------------------------------------------- |
| <mark style="color:blue;">HTTP Method</mark> | Post                                         |

| 파라미터 명                                                    | 입력예시                                                                                                                                                  | 설명                                                                                                                                                                      |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">app\_id</mark>                  | kbe35b81a-5dc6-4cec-ad76-e7bcc3310642                                                                                                                 | \* 스윙투앱에서 발급받은 앱 아이디                                                                                                                                                    |
| <mark style="color:blue;">send\_target\_list</mark>       | targetUserId or -1                                                                                                                                    | <p>*발송할 대상 사용자 아이디</p><p>단일 발송시 user_id</p><p>다중발송시 “,”로 구분하여 입력</p><p>ex:)  user_id1,user_id2</p><p>전체 발송시 -1 입력</p><p>ex:) -1</p>                                     |
| <mark style="color:blue;">send\_target\_type\_list</mark> | MEMBER or ALL\_TARGET                                                                                                                                 | <p>* 개별 사용자에게 보낼경우 개수만큼 MEMBER 라고 입력 ‘,’로 구분하여</p><p>( 예 : ‘MEMBER,MEMBER’ ),</p><p>전체에게 발송할 경우 ‘ALL_TARGET’ 이라고 넣는다.</p><p>( 예 : ‘ALL_TARGET’ ),</p>                   |
| <mark style="color:blue;">send\_type</mark>               | push                                                                                                                                                  | \* 푸시 발송이기 때문에 ‘push’ 라고 입력                                                                                                                                             |
| <mark style="color:blue;">message\_json</mark>            | { “messageTitle” : “내용” , “messageContent” : “내용” , “messageLinkUrl” : “http://m.naver.com” , “messageImageUrl” : “http://www.swing2app.com/abc.png”} | <p>* JSON 형식문자열에 맞게 아래 변수 입력</p><p>messageTitle:제목,</p><p>messageContent:내용</p><p>messageLinkUrl:링크주소</p><p>messageImageUrl:이미지 주소</p><p>*링크주소와 이미지 주소가 없을 경우 생략 가능</p> |
| <mark style="color:blue;">api\_user</mark>                | help@swing2app.com                                                                                                                                    | \* 스윙투앱 사용자 아이디                                                                                                                                                         |
| <mark style="color:blue;">api\_key</mark>                 | abewfw235ksie8d                                                                                                                                       | \* 스윙투앱에서 발급받은 API KEY                                                                                                                                                  |

<mark style="color:orange;">**\* 발급이 필요한 앱 아이디, API KEY 는 고객센터에 요청하시면 발급이 가능합니다.**</mark>

<mark style="color:blue;">\[javascript 구현 예시 – 전체발송]</mark>

```
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

```
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
