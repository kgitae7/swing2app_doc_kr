---
description: 웹사이트의 회원을 스윙투앱 콘솔에 등록하는 작업
---

# 웹사이트 회원 연동 가이드

회원연동방법(웹사용자를스윙투앱앱서비스에등록하는작업)&#x20;

웹 사이트 회원을 스윙투앱 DB 에 기기와 함께 매칭하여 등록하는 작업 입니다.&#x20;

회원 연동을 위해서 javascript 삽입 요청 드립니다.&#x20;

공통 헤더(모든 화면에 해당 스크립트가 들어가도록)에 아래의 문장 삽입해주세요.&#x20;

아래의 사용자 아이디는 웹에서 사용하는 사용자를 의미합니다.

{% hint style="info" %}
연동 작업이 어려우실 경우 스윙투앱 고객센터를 통해 연동 작업 요청해주시면

개발팀에서 연동 작업을 도움드릴 수 있습니다.(비용발생)

고객센터 이메일 : help@swing2app.co.kr
{% endhint %}

### - 로그인 되었을때 삽입하는 코드

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_02_28_002/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLogin("사용자 아이디"," 사용자 이름");
});
</script>
```
{% endcode %}

ex:) 사용자 아이디 : test\_account , 사용자 이름 : test\_name 일 경우

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_02_28_002/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLogin("test_account","test_name");
});
</script>
```
{% endcode %}

### - 회원아이디와 그룹명을 지정해서 로그인하고 싶을때 삽입하는 코드

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_02_28_002/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLoginWithGroup("test_account","test_name","회원그룹명");
});
</script>
```
{% endcode %}

<mark style="background-color:blue;">\*js lib 2024\_11\_24\_001 버전 부터 사용 가능</mark>

<mark style="background-color:blue;">\*앱 제작일시 2024년 11월 25일 19시 이후 제작된 버전부터 사용가능</mark>

<figure><img src="../../../.gitbook/assets/image (60).png" alt=""><figcaption><p>스윙투앱 콘솔에서 지정한 그룹명을 입력</p></figcaption></figure>

\*회원그룹명은 반드시 스윙투앱 콘솔에서 지정한 그룹명을 입력해야 합니다. 일치하는 그룹명이 없을경우 반영되지 않음.

### - 로그아웃 또는 로그인되지 않았을때 삽입하는 코드

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_02_28_002/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLogout();
});
</script>
```
{% endcode %}

{% hint style="info" %}
js 파일 삽입 요령

(1) js 파일은 한번만 삽입하시면 됩니다.

(2) 웹사이트 공통 헤더와 푸터에 삽입하는 것을 권장드립니다.
{% endhint %}

```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_11_24_001/js/swing_app_on_web.js"></script>
```





\*연동후 앱에서 사이트를 실행한 사용자부터 스윙투앱 콘솔 회원조회화면에서 표시가 됩니다.

연동 전 가입한 이전 회원 목록은 불러오지 못합니다.



회원 연동을 완료후에 푸시 발송 API를 이용하여 웹사이트 자체적으로 푸시를 발송 하실 수 있습니다.

[\[푸시 발송 API 가이드\]](../../server-side-api/push-api-notification.md)



