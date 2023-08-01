---
description: 아이폰 푸시 인증서 등록
---

# 앱스토어 아이폰 푸시 인증서 등록

<figure><img src="../../.gitbook/assets/구분선.PNG" alt=""><figcaption></figcaption></figure>

**앱스토어 아이폰 푸시 인증서 등록**

앱스토어는 앱 등록시 애플에서 사용하는 푸시 인증서를 등록하게 됩니다.

앱스토어 앱 등록시 최초 한번 등록시 멤버십 기간 동안 이용 가능합니다.

단, 해당 매뉴얼은 애플에서 제공한 신규 정책입니다.&#x20;

만약이전 푸시 인증서(1년마다 연장하는 시스템)  사용하셨다면 신규 방법으로 연장처리 해주셔야 영구적으로 이용 가능합니다.&#x20;

푸시 인증서 등록은 사용자분의 애플 개발자 계정으로 앱을 등록하실 경우 직접 진행해주셔야 합니다.

스윙투앱 계정 대리등록 하시는 분들은 해당 사항 없습니다.&#x20;

\*인증서 등록은 Mac 뿐만 아니라 일반 컴퓨터 Window에서도 작업 가능합니다.



<figure><img src="../../.gitbook/assets/구분선.PNG" alt=""><figcaption></figcaption></figure>

**애플 개발자 사이트 접속**

{% embed url="https://developer.apple.com/account" %}

<div align="left">

<figure><img src="../../.gitbook/assets/푸시인증서1.PNG" alt=""><figcaption></figcaption></figure>

</div>

1.[애플 개발자 사이트 ](https://developer.apple.com/account/)접속 로그인해주세요. (애플 개발자 계정 로그인)

2.Team ID 복사

애플 개발자 메인 화면에서 Membership Details  선택

Team ID 값 복사해주세요.

<mark style="color:red;">\*중요\*</mark>

Team ID는 마지막 고급관리에서 입력해야 하는 정보입니다.

복사한 ID는 메모장 등에 붙여넣기 해주세요.



<div align="left">

<figure><img src="../../.gitbook/assets/푸시인증서2.PNG" alt=""><figcaption></figcaption></figure>

</div>

3.Certificates, Identifiers & Profiles 항목

**\[Keys] 선택합니다.**



<figure><img src="../../.gitbook/assets/푸시인증서3.PNG" alt=""><figcaption></figcaption></figure>

4.Keys 옆의 \[+] 버튼을 선택합니다.

5.Key name: Key 이름을 입력해주세요. (key 값은 아무 이름이나 입력해도 됩니다)

6.Apple Push Notification Service 체크박스에 체크해주세요.

7.\[Continue] 클릭



<div align="left">

<figure><img src="../../.gitbook/assets/푸시인증서4.PNG" alt=""><figcaption></figcaption></figure>

</div>

8.\[Register] 클릭

9.\[Download] 버튼 클릭 후 파일 저장

(파일 열지 말고 저장만 해주세요.마지막에 해당 파일 다시 업로드 해야 합니다.)

10.Key ID 복사

<mark style="color:red;">\*중요\*</mark>

Key ID는 마지막 고급관리에서 입력해야 하는 정보입니다.

복사한 ID는 메모장 등에 붙여넣기 해주세요.



<div align="left">

<figure><img src="../../.gitbook/assets/푸시인증서5 (1).PNG" alt=""><figcaption></figcaption></figure>

</div>

[스윙투앱  앱운영 →서비스관리 →앱 고급관리](http://www.swing2app.co.kr/view/app\_advanced\_management)

스윙투앱 앱 고급관리로 화면으로 이동합니다.

11.푸시 인증서 ‘p8’ 선택

12.인증서 업로드 버튼을 눌러 다운받은 파일을 업로드 합니다. (순서 9에서 다운받은 파일)

13\. Key id 값을 입력합니다. (순서 10에서 복사한 값 )

14\. Team id 값을 입력합니다. (순서 2에서 복사한 값 )

15\. \[저장] 클릭하면 완료

