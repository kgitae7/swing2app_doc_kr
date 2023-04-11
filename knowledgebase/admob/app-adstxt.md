---
description: 애드몹 적용 앱) 앱에 app-ads.txt 파일 설정하기
---

# 애드몹 - app-ads.txt 파일 설정하기

<figure><img src="../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

​애드몹을 연결한 앱에서 app-ads.txt 파일을 설정하고 등록하는 방법

해당 가이드는 앱에 애드몹 광고 플러그인을 연결해서, 광고 앱으로 운영 중인 사용자분들에게 해당되는 내용입니다.

{% hint style="info" %}
app-ads.txt 파일이란?

app-ads.txt 파일은 구글 애드몹에서 제공하는 정책으로, 광고 송출에 관련된 보안 시스템입니다.

app-ads.txt 파일은 승인 완료된 채널을 통해서만 앱 광고 인벤토리가 판매될 수 있게 해주는 IAB Tech Lab 이니셔티브입니다.

앱에서 광고를 판매할 수 있는 판매자를 더 효과적으로 관리할 수 있으며, 가짜 인벤토리가 광고주에게 판매되는 것을 방지할 수 있습니다.

app-ads.txt 파일은 광고 거래소, 공급측 플랫폼(SSP), 기타 구매자 및 제3자 공급업체에서 공개적으로 사용 및 크롤링할 수 있습니다.

승인된 앱 판매자(app-ads.txt)는 웹 광고 인벤토리를 보호할 목적으로 설계된 [승인된 디지털 판매자(ads.txt)](https://www.iabtechlab.com/ads-txt/) 표준의 확장 프로그램입니다.

호환성이 확장되어 모바일 앱에 게재되는 광고도 지원합니다.
{% endhint %}

{% hint style="info" %}
app-ads.txt 파일 등록은 필수 인가요?​

필수로 설정해야 하는 항목은 아닙니다. \_권장사항입니다.

app-ads.txt 파일을 등록하지 않아도 앱에서 광고를 송출할 수 있고, 광고 수익을 낼 수 있습니다.

다만, 앱 광고를 운영하면서 보안 및 광고 수익에 영향을 줄 수 있기 때문에 등록하여 사용하는 것을 권장드리고 있습니다.

따라서 스윙투앱에서는 직접 셋팅하여 이용할 수 있도록 쉽고 간단하게 시스템을 구축해놓았습니다.

매뉴얼을 보면서 진행하시면 쉽게 등록이 가능합니다.
{% endhint %}

{% hint style="info" %}
AdMob에서 app-ads.txt 파일을 찾고 확인할 수 있도록 하려면 다음 사항에 유의하세요.

* 앱이 Google Play 또는 Apple App Store에 등록되어 있어야 합니다.
* 앱의 스토어 등록정보에는 개발자 웹사이트가 포함되어야 합니다.
{% endhint %}

{% hint style="info" %}
해당 매뉴얼에서는 다음 내용을 다룹니다.

1단계: 개발자 웹사이트 구축 및 스토어 정보에 개발자 웹사이트 추가하기

2단계: app-ads.txt 파일 확인 및 앱에 코드 스니펫 적용하기

3단계: AdMob이 app-ads.txt 파일을 크롤링하고 확인할 때까지 기다리기

4단계: AdMob 계정에서 app-ads.txt 파일이 확인되었는지 살펴보기
{% endhint %}

<figure><img src="../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2022/07/%EB%8B%A8%EB%9D%BD1-1.png)STEP1. **개발자 웹사이트 구축 및 스토어 정보에 개발자 웹사이트 추가하기**



### **1.개발자 웹사이트를 제출해야 합니다.**

플레이스토어, 앱스토어 출시된 앱에 웹사이트 URL을 제출해야 합니다.

사용자분의 웹사이트가 없을 경우 스윙투앱 공식 홈페이지 URL(https://www.swing2app.co.kr)로 제출할 수 있습니다.

개발자 웹사이트는 블로그, 인스타그램, 유튜브 등의 링크가 아닌 도메인이 들어간 홈페이지를 말합니다.

​

### **2.Google Play**

#### &#x20;**앱 스토어 설정 메뉴 – 연락처 정보에 웹사이트 URL을 추가합니다.**

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2023/02/%EC%8A%A4%ED%86%A0%EC%96%B4%EC%84%A4%EC%A0%95.png" alt=""><figcaption></figcaption></figure>

1. [Play Console](https://play.google.com/apps/publish/signup/)에 로그인합니다.
2. 앱을 선택합니다.
3. 왼쪽 메뉴에서 앱 정보→ 스토어 설정 클릭합니다.
4. 스토어 등록벙보 연락처 세부정보로 스크롤합니다.
5. 개발자 웹사이트 URL을 입력해주세요. \*사용자의 웹사이트가 없으실 경우 스윙투앱 홈페이지(http://www.swing2app.co.kr) 링크로 넣어주셔야 합니다.

### **3.Apple App Store**

&#x20;**스토어 등록정보의 마케팅 URL 입력란에 개발자 웹사이트를 추가합니다.**

앱스토어는 사용자가 직접 등록이 불가합니다.

당사로 앱스토어 업로드 신청을 주실 때 신청서 항목에 마케팅 URL 입력란이 있습니다.

마케팅 URL 입력란에 사용자분의 웹사이트 주소를 넣어주세요. \*없다면 스윙투앱 홈페이지 주소(http://www.swing2app.co.kr)를 입력해주세요.

앱 출시 후 해당 정보로 다시 업데이트 해야 한다면, 앱스토어 업로드티켓(20,000원) 구매 후 다시 신청해주셔야 합니다.



### **4.스토어 업데이트 유무**

스토어 등록정보에 사이트 주소가 이미 등록된 상태라면 업데이트를 다시 하지 않아도 됩니다.

앱 출시 후, 사이트 주소를 추가하여 적용했다면 앱 업데이트를 다시 해야 합니다.

<figure><img src="../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2022/07/%EB%8B%A8%EB%9D%BD1-1.png) **STEP2. app-ads.txt 파일 확인 및 앱에 코드 스니펫 적용하기**

​

### **1. app-ads.txt 파일에 맞춤설정된 코드 스니펫 추가하기**

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2023/02/%EC%95%B1%EC%84%A0%ED%83%9D.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2023/02/%EC%95%B1%EC%84%A0%ED%83%9D2.png" alt=""><figcaption></figcaption></figure>

1. [https://apps.admob.com](https://apps.admob.com/?utm\_source=internal\&utm\_medium=et\&utm\_campaign=helpcentrecontextualopt\&utm\_term=http://goo.gl/6Xkfcf\&subid=ww-ww-et-amhelpv4)에서 AdMob 계정에 로그인합니다.
2. 사이드바에서 앱을 클릭합니다.
3. \[모든 앱 보기]를 클릭합니다.
4. app-ads.txt 탭을 클릭합니다.
5. app-ads.txt 설정 방법을 클릭합니다.
6. 복사할 코드 스니펫 옆에 있는 ![](https://lh3.googleusercontent.com/7kjkT9hCjpcFg8nA83VtPX1vD8WzPm\_Ja0HkVtUTnWJ1kfEGGYlzIq2nY\_\_xF2r9bzc) 을 클릭합니다.

​

### **2.복사한 코드 스니펫을 스윙투앱 \[애드몹 플러그인 설정화면]에서 붙여넣기 해주세요.**

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2023/02/%EC%95%B1%EC%84%A0%ED%83%9D3.png" alt=""><figcaption></figcaption></figure>

1. 서비스관리-애드몹 플러그인 설정 이동
2. 애드몹 플러그인 설정 화면 하단에 있는 “스윙투앱 app-ads.txt 등록하기”를 확인할 수 있습니다.
3. 복사한 코드 스니펫을 app-ads.txt 입력란에 붙여넣습니다.
4. 저장하기 버튼을 선택하면 완료입니다.

{% hint style="danger" %}
<mark style="color:red;">**중요 안내**</mark>

스토어 등록정보에 사이트 주소가 이미 등록된 상태라면, 위에 저장까지만 하면 완료되고 업데이트를 다시 하지 않아도 됩니다.

단, 출시된 이후 app-ads.txt 등록을 위해 스토어에 개발자 사이트 주소를 추가 입력했다면 앱 업데이트를 해주셔야 합니다.

1\)플러그인 화면에 app-ads.txt 등록한 뒤 앱 업데이트를 해주세요 – 스윙투앱 앱제작 화면 이동- 앱 업데이트 버튼 선택

2\)새 버전이 제작되면 플레이스토어, 앱스토어에 새 버전 앱으로 다시 제출하여 업데이트 받아야 합니다.

\*플레이스토어는 직접 업데이트 가능하며, 앱스토어는 업로드 대행만 가능합니다.
{% endhint %}



<figure><img src="../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2022/07/%EB%8B%A8%EB%9D%BD1-1.png) **STEP3. AdMob이 app-ads.txt 파일을 크롤링하고 확인할 때까지 기다리기**

​

AdMob에서 app-ads.txt 파일을 크롤링하고 확인하는 데 최대 24시간이 소요될 수 있습니다.

따라서 완전히 작업이 될 때까지 기다려주세요.

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2023/02/%EC%95%B1%EC%84%A0%ED%83%9D5.png" alt=""><figcaption></figcaption></figure>

1. [https://apps.admob.com](https://apps.admob.com/?utm\_source=internal\&utm\_medium=et\&utm\_campaign=helpcentrecontextualopt\&utm\_term=http://goo.gl/6Xkfcf\&subid=ww-ww-et-amhelpv4)에서 AdMob 계정에 로그인합니다.
2. 사이드바에서 앱을 클릭합니다.
3. 모든 앱을 클릭합니다.
4. app-ads.txt 탭을 클릭합니다.
5. 세부정보를 보려는 앱의 행에서 ![](https://lh3.googleusercontent.com/dW0yyTPf131NnuLju8o-VuiHWYkxcb6MLAfu8hKNjYOoA3euoyQEGc9YiruwUjhzJ9U8=w36-h36) 을 클릭합니다. 그러면 추가 세부정보와 AdMob에서 앱 크롤링 진행 상태를 확인할 수 있습니다.

애드몹에서 app-ads.txt 파일을 확인했고, 크롤링이 실행되고 있다는 메시지를 확인할 수 있습니다.

> AdMob에서 app-ads.txt 파일을 크롤링하고 확인하는 데 최대 24시간이 소요될 수 있습니다.
>
> app-ads.txt 상태가 업데이트되려면 최소 24시간은 기다려야 합니다.
>
> 최근에 Google Play에서 개발자 웹사이트를 추가했거나 Google Play에서 앱 등록정보를 업데이트한 경우 AdMob에서 이러한 변경사항을 감지하는 데 최대 24시간이 걸립니다.



<figure><img src="../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2022/07/%EB%8B%A8%EB%9D%BD1-1.png) **STEP4. AdMob 계정에서 app-ads.txt 파일이 확인되었는지 살펴보기**

​

**등록한 app-ads.txt 파일이 문제가 없는지 확인하는 방법입니다.**

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2023/02/%EC%95%B1%EC%84%A0%ED%83%9D4.png" alt=""><figcaption></figcaption></figure>

AdMob 계정에서 모든 앱의 [app-ads.txt 파일 상태 및 세부정보를 조회](https://support.google.com/admob/answer/9788846)할 수 있습니다.

이렇게 <mark style="color:green;">초록색 상태 불</mark>로,“app-ads.txt 파일을 찾아 확인했습니다. AdMob에서 app-ads.txt 파일을 크롤링하여 확인했습니다.”

메시지가 떠있으면 정상적으로 작업이 완료된 것입니다.

파일을 찾을 수 없거나 파일이 확인되지 않은 경우 AdMob 계정에 제공한 정보를 검토하거나 [app-ads.txt 문제해결](https://support.google.com/admob/answer/9776740)에 대해 자세히 알아볼 수 있습니다.

{% hint style="danger" %}
**안내사항**

app-ads.txt 파일을 등록한다고 해서 앱에서 광고 노출이 더 잘 되거나, 수익을 더 발생시키는 구조가 아닙니다.

앱 내 광고 시스템을 보다 클린하게 보안해주는 개념입니다.

앱에 애드몹 광고를 적용하여 이용하시는 분들은, 스윙투앱에서 제공하는 매뉴얼을 확인하여 운영해주시기 바랍니다.
{% endhint %}





**Related Articles**

* [애드몹 – 광고 노출 권한 설정](https://wp.swing2app.co.kr/knowledgebase/adexposure-permission/)
* [애드몹 – 테스트 아이디 설정](https://wp.swing2app.co.kr/knowledgebase/testad/)
* [애드몹-스윙투앱 계정 초대하기](https://wp.swing2app.co.kr/knowledgebase/admob-invite/)
* [﻿애드몹 플러그인 광고 셋팅 주의사항](https://wp.swing2app.co.kr/knowledgebase/admobplugin-check/)
* [애드몹 플러그인 설정이란?](https://wp.swing2app.co.kr/knowledgebase/admob-pluginsettings/)
* [애드몹 운영 주의사항](https://wp.swing2app.co.kr/knowledgebase/admob-operation/)
