---
description: Firebase 프로젝트를 스윙투앱과 연동하기
---

# Firebase 프로젝트 연동하기(안드로이드)



파이어베이스 제품을 사용하기 위해서는 앱과 Firebase 프로젝트는 연동해야 합니다.

Firebase 프로젝트를 스윙투앱에 연동 면 아래의 단계를 절차대로 진행하시면 됩니다.



1. 파이어베이스 접속

[https://console.firebase.google.com/](https://console.firebase.google.com/)

2. 파이어베이스 콘솔에서 프로젝트 추가

<figure><img src="../../.gitbook/assets/image (48).png" alt="" width="563"><figcaption><p>Firebase Console 화면</p></figcaption></figure>

3. 프로젝트 생성 과정

<figure><img src="../../.gitbook/assets/image (49).png" alt="" width="375"><figcaption><p>프로젝트명 입력</p></figcaption></figure>

* 프로젝트 이름에 원하는 프로젝트명을 입력
* 계속 버튼을 클릭

<figure><img src="../../.gitbook/assets/image (17).png" alt="" width="375"><figcaption></figcaption></figure>

* 애널리틱스 사용설정을 해제(프로젝트 생성 후, 애널리틱스를 설정 가능합니다.)
* 프로젝트 만들기 클릭

<figure><img src="../../.gitbook/assets/image (50).png" alt="" width="375"><figcaption><p>  </p></figcaption></figure>

* 로딩이 지난 후에 완료 메시지가 나온다면
* "계속"  버튼에 대한 클릭



<figure><img src="../../.gitbook/assets/image (18).png" alt="" width="563"><figcaption></figcaption></figure>

* "프로젝트 설정"을 클릭

<figure><img src="../../.gitbook/assets/image (19).png" alt="" width="563"><figcaption></figcaption></figure>

* 아래의 스크롤 후에 "안드로이드" 클릭

<figure><img src="../../.gitbook/assets/image (20).png" alt="" width="359"><figcaption></figcaption></figure>

* "Android 패키지 이름"에 앱 안드로이드 패키지 아이디를 입력후 "앱 등록" 클릭

&#x20;     ( 반드시 스윙투앱에서 사용중인 안드로이드 패키지 아이디를 입력해야 합니다. )

&#x20;      스윙투앱에서 사용중인 패키지 아이디를 확인하는 방법

&#x20;      "앱 제작" -> "고급 설정" -> "앱 제작 설정" -> "안드로이드 패키지아이디" -> Edit 클릭

<figure><img src="../../.gitbook/assets/image (21).png" alt="" width="455"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (22).png" alt="" width="563"><figcaption></figcaption></figure>

* "google-service.json 다운로드" 버튼 클릭
* 다운로드 받은 파일을 "앱 제작" -> "고급 설정" -> "앱 제작 설정" -> "파이어베이스 프로젝트 json파일" -> Edit 클릭후 파일 업로드

<figure><img src="../../.gitbook/assets/image (23).png" alt="" width="563"><figcaption></figcaption></figure>

* 다운로드 후 "다음" 버튼을 클릭
* Firebase SDK 추가 부분도 "다음" 버튼을 클릭

<figure><img src="../../.gitbook/assets/image (24).png" alt="" width="375"><figcaption></figcaption></figure>

* "콘솔로 이동" 버튼을 클릭하면 안드로이드 앱 셋팅은 모두 완료

<figure><img src="../../.gitbook/assets/image (25).png" alt="" width="375"><figcaption></figcaption></figure>



모든 작업을 완료후에 앱 제작을 다시 하시면 Firebase 와 연동된 앱을 확인하실 수 있습니다.

