---
description: 아임웹(imweb.me) 웹사이트에 간단한 코드삽입으로 회원연동 활용 가이드
---

# 아임웹 웹사이트 회원 연동 가이드

나만의 아임웹(imweb.me) 웹사이트에 사용자들이 로그인할 경우 스윙투앱 앱과의 상호 연동을 위해서

필요한 작업들을 소개하도록 하겠습니다.

회원연동을 완료하면 스윙투앱 콘솔에서 웹사이트의 회원을 조회할 수 있으며

연동된 회원을 통해서 웹사이트의 개별 회원에게 푸시 메시지를 발송할 수 있습니다.



## 1. 회원연동 가이드

### 1.1 아임웹(imweb.me) Dashboard 이동 후 연동코드 삽입



<figure><img src="../../../.gitbook/assets/image (53).png" alt=""><figcaption><p>아임웹 콘솔화면</p></figcaption></figure>

2번 Footer Code 항목에 아래의 코드 삽입후 저장

```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_02_28_002/js/swing_app_on_web.js"></script>
<script>
  if( $('.profile-area .member-info .email-info').length > 0 && $('.profile-area .member-info .email-info').text() != '' )
  {
	  swingWebViewPlugin.app.login.doAppLogin($('.profile-area .member-info .email-info').text(),$('.profile-area .member-info .email-info').text());
      console.log('login user id : ' + $('.profile-area .member-info .email-info').text());
  }
  else
  {
	swingWebViewPlugin.app.login.doAppLogout(); 
	console.log('logout');
  }

</script>
```

###

### 1.2 회원연동 확인 작업

&#x20;     연동 작업을 모두 진행하셨다면 앱으로 웹사이트를 실행후 스윙투앱 콘솔화면 접속 후에

&#x20;     푸시&회원 -> 회원조회 화면에 들어가서 웹사이트 회원이 조회가 되는지 확인된다면&#x20;

&#x20;     정상적으로 연동된 것입니다.



<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption><p>스윙투앱 콘솔화면에서 아임웹 회원 연동이 확인된 화면</p></figcaption></figure>



