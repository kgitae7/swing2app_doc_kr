---
description: Firebase 의 Dynamic Links 를 스윙투앱과 연동하기
---

# Dynamic Links 연동

파이어 베이스 콘솔에서 프로젝트를 선택해주세요.

1. Firebase Console 접속 [https://console.firebase.google.com/](https://console.firebase.google.com/) 로그인

이후에 생성한 프로젝트를 선택해주세요.

<figure><img src="../../.gitbook/assets/image (39).png" alt="" width="375"><figcaption></figcaption></figure>

2. 프로젝트 접속후 "참여" -> "Dynamic Links" 를 클릭

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

3. 계속하기 클릭

Firebase Dynamic Links 는 현재 25년 8월25일까지만 지원되니 참고해주세요.

만료일전에 대체 기술이 개발될 예정이니 그전까지는 Firebase Dynamic Links 로 활용할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (42).png" alt="" width="563"><figcaption></figcaption></figure>

안내 문구를 체크하고 "계속"을 클릭

<figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

동적링크를 사용할 주소를 입력해주세요.

Firebase 에서 제공하는 도메인은 page.link 입니다.

따라서 testdnlink1.page.link 이런식으로 입력이 가능합니다.

자신의 도메인을 직접 사용하려면 Firebase 를 이용하여 웹사이트를 구축하였거나&#x20;

DNS 에 Firebase 호스트를 등록해야 한다.

따라서 특별한 경우가 아니라면 Firebase 제공하는 기본 도메인을 활용할 것을 권장드립니다.

(Deeplink 의 링크들 최종적으로 다른 주소로 Redirect 되기 때문에 사용자들에게 보여지지 않는 주소 입니다. 따라서 Firebase 기본 도메인을 사용해도 특별한 문제는 없습니다.)

아래의 화면에서 동적링크 주소를 입력했다면 "계속"을 클릭

<figure><img src="../../.gitbook/assets/image (44).png" alt="" width="533"><figcaption></figcaption></figure>

정상적으로 처리되었다면 아래의 화면이 나오고 "완료" 버튼을 누르면 된다.

<figure><img src="../../.gitbook/assets/image (45).png" alt="" width="536"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption><p>셋팅완료 화면</p></figcaption></figure>

이제 입력한 동적링크 주소 스윙투앱에 셋팅만 해주면 모두 완료가 된다.



"앱 제작" -> "고급 설정" -> "앱 제작 설정" -> "Firebase Dynamic Link" -> Edit 클릭 후&#x20;

동적링크 주소를 입력해주시면 됩니다. http를 제외하고 다음과 같이 입력

예:) testdnlink.page.link

<figure><img src="../../.gitbook/assets/image (47).png" alt="" width="375"><figcaption></figcaption></figure>



입력을 완료후에 앱 제작을 다시 하시면 Firebase Dynamic 링크와 연동된 앱을 확인하실 수 있습니다.

Firebase Dynamic Links 사용법은 아래의 도움말을 참고하시면 됩니다.



