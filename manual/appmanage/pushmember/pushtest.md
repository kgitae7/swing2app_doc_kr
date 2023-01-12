---
description: 테스트 푸시 발송 이용방법, 푸시 테스트 기기 등록 방법
---

# 푸시 장치 관리 이용방법

<figure><img src="../../../.gitbook/assets/구분선.PNG" alt=""><figcaption></figcaption></figure>

### 푸시 장치 관리 기능이란?



**특정 핸드폰 기기를 테스트 기기로 등록하여, 해당 기기에만 테스트용 푸시를 발송 할 수 있는 기능입니다.**

푸시버전으로 제작한 앱은 앱 운영자가 푸시가 잘 들어오는지 테스트를 하고 싶어도 전체발송 밖에는 할 수 없었어요.

\*푸시앱은 앱에서 회원가입이 없기 때문에 모든 앱 설치자가 손님으로 표시되며, 회원을 선택할 수가 없습니다.

따라서 푸시 장치 관리 기능을 이용하여 운영자 핸드폰을 테스트 기기로 등록 한다음, 푸시발송 메뉴에서 테스트 발송하기를 하면 테스트로 등록한 핸드폰으로만 푸시가 들어오게 됩니다.

푸시 장치 관리는 새롭게 추가된 기능으로 **\[푸시 장치 관리] 기능을 이용하여 테스트 기기 등록을 한 뒤, 푸시발송하기에서 테스트 발송하기로 푸시 테스트를 이용할 수 있습니다.**

{% hint style="warning" %}
\*푸시장치 관리는 안드로드이폰에서만 푸시 테스트가 가능합니다. (아이폰 불가)

\*푸시앱제작시 “툴바 표시 여부 – 툴바 제거”로 선택하고 제작하신 앱은 푸시 장치 관리 기능 테스트가 불가합니다.

\*해당 기능은 2020년 3월 업데이트 된 기능입니다. 2020년 3월 이전에 제작한 앱은 새로 업데이트 하신 뒤 이용해주시기 바랍니다.
{% endhint %}

&#x20;****&#x20;

<figure><img src="../../../.gitbook/assets/구분선.PNG" alt=""><figcaption></figcaption></figure>

### STEP1. 푸시 장치 관리 이동

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C%EC%9E%A5%EC%B9%98%EA%B4%80%EB%A6%AC2.png)

[앱운영 → 푸시&회원 → \[푸시 장치 관리\]](http://www.swing2app.co.kr/view/push\_device\_management)로 이동합니다.



![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C%EC%9E%A5%EC%B9%98%EA%B4%80%EB%A6%AC3.png)

푸시 장치 관리 페이지에는 앱을 설치한 핸드폰 기기 목록을 확인할 수 있어요.

내 핸드폰의 ‘**device\_token**‘ 을 확인하여 해당되는 기기의 **\[테스트 등록]** 버튼을 누르면 해당 기기가 테스트로 등록됩니다.

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%99%94%EC%82%B4%ED%91%9C-2.png)

**▶ **<mark style="color:purple;">**안드로이드폰에서 device\_token은 어떻게 확인할 수 있나요?**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C%EC%9E%A5%EC%B9%98%EA%B4%80%EB%A6%AC5.png)

핸드폰에서 앱을 실행한 뒤 푸시 툴바의 설정(톱니바퀴 모양)버튼을 탭해주세요.

그럼 이미지처럼 \[푸시 메시지 수신 설정] 배너 창이 뜨구요.

해당 배너를 3\~4번 탭해주세요.

<mark style="color:red;">\*안드로이드폰에서만 확인 가능합니다.</mark>&#x20;

​

<mark style="color:blue;">**\[움짤 이미지로 확인하기]**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%EB%85%B9%ED%99%94\_2020\_03\_03\_17\_15\_56\_544.gif)

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C%EC%9E%A5%EC%B9%98%EA%B4%80%EB%A6%AC6.png)

탭한 자리 위로 해당 핸드폰의 ​<mark style="color:blue;">**device info**</mark>배너 창이 뜹니다.

해당 정보가 device\_token 정보가 됩니다.

따라서 푸시 장치 관리에서 해당 디바이스 정보와 동일한 기기를 확인하여 테스트로 등록할 수 있습니다.



![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%ED%86%A0%ED%81%B0.png)

만약 앱에 등록된 기기가 많아 device\_token을 찾기 어렵다면, 상단의 검색창에서 device 정보를 입력하여 조회할 수 있어요!

<figure><img src="../../../.gitbook/assets/구분선.PNG" alt=""><figcaption></figcaption></figure>

### STEP2. 테스트 푸시 발송하기

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C%EC%9E%A5%EC%B9%98%EA%B4%80%EB%A6%AC4.png)

앱운영 → 푸시&회원 → 푸시발송하기 이동합니다.

**기본설정에서 \[테스트 발송하기]에 체크해주세요.** \*테스트로 등록된 기기에만 푸시가 발송이 됩니다.

​

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/03/%ED%91%B8%EC%8B%9C%EC%9E%A5%EC%B9%98%EA%B4%80%EB%A6%AC7.png)

다음 \[푸시보내기]는 기존 푸시발송 내용과 동일합니다.&#x20;

내용 입력해서 푸시발송하기 선택해주세요.

<figure><img src="../../../.gitbook/assets/구분선.PNG" alt=""><figcaption></figcaption></figure>

​푸시 장치 관리는 푸시버전앱에서 유용하게 사용할 수 있는 기능입니다.

푸시앱에서, 푸시 알림이 잘 들어오는지 테스트가 필요할 때 앱 운영자 기기를 테스트로 등록한 뒤 푸시 발송 테스트를 해볼 수 있습니다.&#x20;

**푸시장치 관리는 안드로드이폰에서만 푸시 테스트가 가능합니다. (아이폰 이용 불가)**

****

****
