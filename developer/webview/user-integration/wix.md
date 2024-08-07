---
description: Wix 웹사이트에 간단한 코드삽입으로 회원연동 활용 가이드
---

# Wix 웹사이트 회원 연동 가이드

나만의 Wix 웹사이트에 사용자들이 로그인할 경우 스윙투앱 앱과의 상호 연동을 위해서

필요한 작업들을 소개하도록 하겠습니다.

회원연동을 완료하면 스윙투앱 콘솔에서 웹사이트의 회원을 조회할 수 있으며

연동된 회원을 통해서 웹사이트의 개별 회원에게 푸시 메시지를 발송할 수 있습니다.



## 1. 회원연동 가이드

### 1.1 Wix Dashboard 이동 하기

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Wix 콘솔화면</p></figcaption></figure>

### 1.2 홈화면에 Embed HTML 요소 삽입하기

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Wix 콘솔화면 </p></figcaption></figure>

### 1.3 HTML 요소에 소스 삽입하기

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption><p>Wix 콘솔화면 </p></figcaption></figure>

(1) 번 영역에 아래의 코드를 삽입하기

{% code title="HTML 요소 코드" lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2022_06_17_001/js/swing_app_on_web.js"></script>

<script>
 window.onmessage = (event) => {
    if (event.data) {
       let receivedData = event.data;
      	console.log('login account : ' + receivedData.id + ',' + receivedData.name);
      swingWebViewPlugin.app.login.doAppLogin(receivedData.id,receivedData.name);
    }
  };
  
</script>

```
{% endcode %}



### 1.4 HTML 요소에 아이디를 부여하기

<figure><img src="../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption><p>Wix 콘솔화면 </p></figcaption></figure>

(1) 생성한 HTML 요소에 ID 를 부여하기&#x20;

&#x20;   다음의 아이디로 반드시 부여해주세요 ID 값 swing2appLogin

### 1.5 페이지 코드 삽입하기 ( 최종단계 )

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Wix 콘솔화면 </p></figcaption></figure>

(1) Home 화면 클릭후 (2) 번 항목 소스 영역에 아래의 코드를 삽입

아래의 코드를 삽입하였다면 모든 작업이 완료되었습니다.

저장후 배포를 하시면 정상 동작할 것입니다.

{% code title="Wix Home 화면에 삽입할 코드" lineNumbers="true" %}
```javascript
import wixUsers from 'wix-users';
import { currentMember } from 'wix-members-frontend';
$w.onReady(function () {
    if (wixUsers.currentUser.loggedIn) {
        currentMember.getMember('FULL')
            .then((member) => {
                const id = member._id;
                const fullName = `${member.contactDetails.firstName} ${member.contactDetails.lastName}`;
                $w("#swing2appLogin").postMessage({
                    id : id ,
                    name : fullName
                });
                return member;
            })
            .catch((error) => {
                console.error(error);
            });
    }
    else{
        console.log('guest login');
        $w("#swing2appLogin").postMessage({
            id : null ,
            name : null
        });
    }
});

```
{% endcode %}



### 1.6 회원연동 확인 작업

&#x20;     연동 작업을 모두 진행하셨다면 앱으로 웹사이트를 실행후 스윙투앱 콘솔화면 접속 후에

&#x20;     푸시&회원 -> 회원조회 화면에 들어가서 웹사이트 회원이 조회가 되는지 확인된다면&#x20;

&#x20;     정상적으로 연동된 것입니다.

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>스윙투앱 콘솔화면에서 Wix 회원 연동이 확인된 화면</p></figcaption></figure>



