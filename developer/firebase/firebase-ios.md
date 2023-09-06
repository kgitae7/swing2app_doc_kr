---
description: Firebase 프로젝트를 스윙투앱과 연동하기
---

# Firebase 프로젝트 연동하기(iOS)

파이어베이스 제품을 사용하기 위해서는 앱과 Firebase 프로젝트는 연동해야 합니다.

Firebase 프로젝트를 스윙투앱에 연동을 하려면 아래의 단계를 절차대로 진행하시면 됩니다.



1. 파이어베이스 접속 후 구글 아이디로 로그인

&#x20;       [https://console.firebase.google.com/](https://console.firebase.google.com/)

2. 파이어베이스 콘솔에서 프로젝트 만들어진 프로젝트를 선택

( 프로젝트를 최초 생성을 해야 한다면 [Firebase 프로젝트 연동하기(안드로이드 부분을 참고해주세요)](firebase.md) )

<figure><img src="../../.gitbook/assets/image (48).png" alt="" width="563"><figcaption><p>Firebase Console 화면</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (18).png" alt="" width="563"><figcaption></figcaption></figure>

* "프로젝트 설정"을 클릭



<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

* 아래의 스크롤 후에 "앱추가"를 클릭

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

* "iOS" 항목을 클릭

<figure><img src="../../.gitbook/assets/image (30).png" alt="" width="318"><figcaption></figcaption></figure>

* "Apple 번들 ID"에 앱 번들 아이디를 입력후 "앱 등록" 클릭

&#x20;     ( 반드시 스윙투앱에서 사용중인 앱 번들 아이디를 입력해야 합니다. )

&#x20;      스윙투앱에서 사용중인 애플번들 아이디를 확인하는 방법

&#x20;      "앱 제작" -> "고급 설정" -> "앱 제작 설정" -> "애플번들ID" -> Edit 클릭

<figure><img src="../../.gitbook/assets/image (21).png" alt="" width="455"><figcaption></figcaption></figure>

* "GoogleService-Info.plist 다운로드" 버튼 클릭

<figure><img src="../../.gitbook/assets/image (31).png" alt="" width="563"><figcaption></figcaption></figure>



* 다운로드 받은 파일을 "앱 제작" -> "고급 설정" -> "앱 제작 설정" -> "파이어베이스 프로젝트 plist 파일(iOS용)" -> EDIT 클릭후 파일 업로드

<figure><img src="../../.gitbook/assets/image (32).png" alt="" width="375"><figcaption></figcaption></figure>



* 업로드 완료후 Firebase  화면으로 돌아와 "다음" 버튼을 클릭
* Firebase SDK 추가 부분과 초기화 코드 부분도 모두 "다음" 버튼을 클릭

<figure><img src="../../.gitbook/assets/image (33).png" alt="" width="375"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (35).png" alt="" width="375"><figcaption></figcaption></figure>

* 마지막 단계에서 "콘솔로 이동" 버튼을 클릭하면 iOS 앱 셋팅은 모두 완료

<figure><img src="../../.gitbook/assets/image (37).png" alt="" width="318"><figcaption></figcaption></figure>

모든 작업을 완료후에 앱 제작을 다시 하시면 Firebase 와 연동된 앱을 확인하실 수 있습니다.

