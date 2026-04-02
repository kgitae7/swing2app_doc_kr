---
description: 플레이스토어 내부테스트 등록방법 완벽 가이드
---

# 구글 플레이스토어 내부 테스트 방법

***

**플레이스토어에서 내부테스트를 등록하고, 앱을 설치하는 방법 알려드립니다.**

{% hint style="success" %}
#### **💡내부 테스트는 왜? 어떤 경우에 하나요?**

구글 플레이 내부 테스트는 앱을 실제 사용자에게 공개하기 전에 안정성과 정책을 점검하기 위해서 진행됩니다.

특히 아래와 같은 목적에서 반드시 진행하는 것이 좋습니다.

✔️ 앱 오류(크래시, UI 깨짐 등) 사전 확인

✔️ 로그인, 결제, 푸시 등 핵심 기능 정상 동작 확인

✔️ 실제 기기 환경에서 테스트 (다양한 안드로이드 버전 대응)

✔️ 플레이스토어 심사 전 리스크 최소화

✔️ 팀원 또는 고객사와 함께 사전 검수 진행

👉 쉽게 말하면“스토어에 올리기 전에 실제 환경에서 미리 써보는 단계” 라고 보시면 됩니다.
{% endhint %}

***



## STEP1. 앱만들기

구글플레이 콘솔 접속 [https://play.google.com/console/developers/](https://play.google.com/console/developers/)

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

\[앱 만들기] 선택해주세요.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

1\)앱이름 (플레이스토어 출시되는 이름) \*나중에 수정 가능하오니 임시로 입력하셔도 됩니다.

2\)기본언어: 한국어 선택 (특정 국가에 배포되어야 한다면 해당 언어로 선택합니다. 예)미국)

3\)앱 또는 게임 선택: 앱으로 선택해주세요.

4\)유료 또는 무료 선택 (앱을 유료로 판매할 경우 ‘유료’ 선택, 무료 선택시 이후에 유료로 변경할 수 없습니다)

5\)개발자 프로그램 정책 체크

6\)Play앱 서명 체크

7\)미국 수출법규 체크

8\)\[앱 만들기] 버튼 선택합니다.

***



## STEP2.내부 테스트 등록 시작

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

왼쪽 카테고리에서 테스트 및 출시 선택

1.테스트- '내부 테스트'를 선택해주세요.

2.테스터 메뉴 클릭

3.이메일 및 목록 만들기



<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

이메일 목록에서

4.목록 이름 입력 \*어디 노출되는 것이 아니므로 구분하기 편한 이름으로 기재해주세요. 수정도 가능합니다.

5.이메일주소 추가 \*테스트 하고자 하는 이메일주소를 모두 입력해주세요.

-이메일주소 몇개 안되면 쉼표로 구분해서 Entrer키를 눌러 목록에 추가합니다.

-테스트할 메일주소가 많다면 csv파일로 한 번에 올려주세요.

6.변경사항 저장

7.만들기 선택

​

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

8.저장 \*추가된 이메일주소 잘 등록되었으면 저장 버튼 탭합니다.

이메일주소는 언제라도 다시 수정 및 추가 가능합니다.



<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

9.'출시'로 이동해주세요.

10.새 버전 만들기



<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

11.업로드를 클릭하여 aab파일을 올려주세요.

12.파일이 잘 올라갔다면, 다음 버튼을 눌러주세요.



<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

13.저장 및 출시 버튼

14.최종 저장 및 출시 선택합니다.



이렇게까지 하면 내부 테스트 등록이 완료된 것이구요.

보통 1시간 이내 내부테스트 설치 링크를 받을 수 있습니다.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

다시 내부 테스트의 "테스터"로 이동하면

15.테스트 참여 방법에 웹에서 참여 "링크복사"버튼이 활성화 됨을 확인할 수 있습니다.

"링크 복사"를 선택해서 공유하고자 하는 곳을 링크를 붙여넣기 해주세요.

테스터들에게 메일로 전송하거나 메신저 등 대화가 가능한 채널을 통해 링크를 보내주세요.

***

## STEP.3 안드로이드폰에서 테스트 앱 설치 받기

<div align="left"><figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure></div>

1.메신저 어플로 공유된 링크주소 터치



<div align="left"><figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure></div>

2.구글 플레이 페이지로 이동하며, 하단 \[Accept invite] 버튼 눌러주세요.



<div align="left"><figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure></div>

3.앱을 다운받을 수 있는 링크가 제공됩니다.

<mark style="color:$primary;">download it on Google Play</mark>

혹은

<mark style="color:$primary;">install the public version on Google Play</mark> 링크로 선택하면 됩니다.



<div align="left"><figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure></div>

4.앱 설치화면으로 이동하며, 설치를 누르고 앱 다운을 진행합니다.



<div align="left"><figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure></div>

5.완료, 앱 열기를 탭해서 핸드폰에서 앱을 실행하여 테스트해주세요.

***



## 📌 내부 테스트는 언제 진행해야 할까?

아래 상황이라면 내부 테스트를 꼭 진행하세요.

1️⃣ 앱 개발 완료 직후

* 기능 개발이 끝났지만 아직 배포 전인 상태
* QA(품질 테스트) 단계

2️⃣ 스토어 심사 전에 마지막 점검

* 정책 위반 여부 확인
* 로그인, 결제, 개인정보 처리 흐름 검증

3️⃣ 업데이트 배포 전

* 기존 앱에 기능 추가/수정이 있을 때
* 오류 없이 정상 작동하는지 확인

4️⃣ 고객사 또는 내부 관계자 검수 필요할 때

* 실제 사용자처럼 사용해보는 테스트

***



## ❓ 자주 묻는 질문 (FAQ)

Q1. 내부 테스트하면 구글 심사를 받나요?

👉 아닙니다. 내부 테스트는 심사 없이 바로 배포 가능합니다. (테스터에게만 공개)

등록 즉시 참여 URL링크 생성됩니다.

​

Q2. 누구나 앱을 설치할 수 있나요?

👉 아닙니다. 초대된 테스터만 설치 가능합니다.

이메일 초대 방식으로, 테스트를 하고자 하는 사용자의 메일주소를 등록해서 이용해주세요.

메일은 반드시 구글 gmail로만 이용 가능합니다.

​

Q3. 내부 테스트 앱은 스토어에 노출되나요?

👉 아닙니다. 일반 사용자에게는 절대 노출되지 않습니다.

​

Q4. 내부 테스트 → 정식 출시로 바로 전환 가능한가요?

👉 가능합니다. 같은 앱으로 프로덕션 트랙으로 승격하면 됩니다.

​

Q5. 내부 테스트는 몇 명까지 가능한가요?

👉 테스터는 최대 100명까지 참여 가능합니다.

​

Q6. 내부 테스트도 업데이트가 가능한가요?

👉 가능합니다. AAB 재업로드 시 테스터에게 자동 업데이트됩니다<br>

***
