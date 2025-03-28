---
description: 푸시 아이콘 이미지 디자인 가이드라인
---

# 푸시 아이콘 이미지 가이드라인

<figure><img src="../../../.gitbook/assets/구분선 (1) (1) (1).PNG" alt=""><figcaption></figcaption></figure>

### ![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%8B%A8%EB%9D%BD1-1.png) **1.푸시란, 푸시 아이콘 이미지란?**

![](https://wp.swing2app.co.kr/wp-content/uploads/2022/11/%ED%91%B8%EC%8B%9C%EB%9E%80_886-847x1024.png)

푸시는 일반 프로토타입 앱, 푸시전용 앱에서 이용할 수 있는 기능이구요.

앱을 설치한 사용자들에게 공지, 업데이트 등의 알림이 있을 경우 앱 내에서 메시지를 보내는 것을 ‘푸시’ 라고 합니다.

그리고 **푸시가 발송되면 제목과 메시지 옆에 보여지는 이미지를 푸시 아이콘이라고 합니다.**

푸시 발송시 보여지는 아이콘은 앱 아이콘 이미지로 자동 셋팅되어 발송되며, 푸시 발송용 아이콘 이미지를 별도 설정하여 발송할 수도 있습니다.&#x20;

(푸시 발송용 아이콘 이미지는 안드로이드폰에서만 지원)



### ![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%8B%A8%EB%9D%BD1-1.png) **2.푸시 아이콘 이미지 에러 문제**

푸시 발송시, 푸시 아이콘 이미지가 지정된 이미지로 보이지 않고 회색 네모칸으로 보여지는 경우가 있습니다.&#x20;

\=>이유는 아이콘 이미지에 지정된 색상이 안드로이드폰에서 지원하지 않은 색상이기 때문입니다.

<mark style="color:green;">이미지 참고)</mark>

<div align="left"><figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2022/11/%ED%91%B8%EC%8B%9C%EC%95%84%EC%9D%B4%EC%BD%98.png" alt=""><figcaption></figcaption></figure></div>

안드로이드 스펙에 맞는 notification설정을 해야 하는데 등록된 이미지 색상 배합이 스펙에 맞지 않아 발생한 문제에요.



### ![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%8B%A8%EB%9D%BD1-1.png) **3.안드로이드 아이콘 색상 지원**

안드로이드폰은 \*\* **GrayScale(흑백,검정,회색,흰색) 색상을 지원하지 않습니다.**&#x20;

흰색/검정/회색/흑백 등의 배경색을 입혀서 제작했다면, 안드로이드 기기에서 아이콘 이미지를 인식하지 못해 자동으로 이미지를 회색으로 변경하여 출력합니다. &#x20;



### ![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%8B%A8%EB%9D%BD1-1.png) **4.아이콘 이미지 색상 가이드&#x20;**<mark style="color:red;">**\*중요\***</mark>

1\)아이콘을 배경을 투명으로 만들어서 사용(모든 안드로이드 기기 동작)

2\)배경을 넣을 경우, 그외 색은 GrayScale(흑백,검정,회색,흰색)을 피해서 제작 (삼성 기기 모두 동작 , 일부 기기에서 정상 표시 안됨 )

위의 2가지 중 하나를 만족시키면 정상적으로 동작합니다.&#x20;

단, 범용적 사용을 위해서 투명 이미지로 제작하는 것을 권장드립니다.&#x20;

-아이콘 이미지 변경은 앱 업데이트가 필요합니다. 아이콘 이미지 변경 후 앱 업데이트를 해주세요.&#x20;

-새 버전으로 업데이트 받은 뒤, 푸시 발송하기를 진행하면 변경된 푸시 아이콘 이미지로 발송됩니다.

-플레이스토어에 출시된 앱은, 새로 제작된 버전의 앱으로 플레이스토어에 업데이트를 다시 해주셔야 합니다.

**\[guideline 참조]**

{% embed url="https://m2.material.io/design/platform-guidance/android-notifications.html#types-of-notifications" %}

모든 안드로이드 폰에서 아이콘 이미지가 출력되기 위해서는 아래 방법으로 디자인해주셔야 합니다.&#x20;

<mark style="color:blue;">**푸시 아이콘 이미지는 투명 배경 필수 + 흰색으로 표시된 이미지를 사용하시는 것이 좋습니다.**</mark>

**가이드 링크 보기)**

{% embed url="http://romannurik.github.io/AndroidAssetStudio/icons-notification.html#source.type=clipart&source.clipart=ac_unit&source.space.trim=1&source.space.pad=0&name=ic_stat_onesignal_default" %}

### ![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%8B%A8%EB%9D%BD1-1.png) **5.**&#xD478;시 아이콘 이미지 디자인 가이드



1\)앱 아이콘 이미지를 만들 때는 디자인 전문 편집도구 – 포토샵, 일러스트 등으로 제작해주시길 권장드려요.

그림판, 파워포인트 등으로 작업시 화질이 생각보다 안좋을 수 있어요!

2\)아이콘 안에 들어간 디자인 영역이 너무 클 경우 핸드폰에서 이미지가 잘려서 표시할 수 있어요.

따라서 이미지 제작시 영역에 꽉 차지 않게, 조금 여유 있게 작업해주세요.

3\)아이콘은 앱의 스타일, 브랜드, 로고 등을 생각하여 별도 디자인 제작을 해서 넣어주셔야 합니다.

4\)아이콘 모양은 정사각형으로 만들어주세요. 원 모양, 세모 모양 등 다른 도형으로 설정하지 않도록 해주세요.



### ![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%8B%A8%EB%9D%BD1-1.png) **6.푸시 아이콘 이미지 등록방법**

푸시 발송시, 아이콘은 앱제작시 등록한 아이콘 이미지로 보여집니다.

따라서 앱제작시 앱 아이콘 이미지 등록란에 위의 가이드라인을 맞춰서 이미지를 넣으시면 푸시 아이콘 이미지도 정상적으로 출력이 되구요.&#x20;

별도 설정하지 않아도 앱 아이콘 이미지로 푸시 아이콘이 자동 설정됩니다.

{% hint style="info" %}
**중요 팁!!**

앱 아이콘 이미지와 다른 푸시용 아이콘 이미지를 따로 설정할 수도 있습니다.

스윙투앱 앱제작 – 고급설정 메뉴-안드로이드 푸시 아이콘 메뉴에서 이미지를 등록할 수 있어요.
{% endhint %}

<figure><img src="https://wp.swing2app.co.kr/wp-content/uploads/2022/11/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%ED%91%B8%EC%8B%9C%EC%95%84%EC%9D%B4%EC%BD%98_886.png" alt=""><figcaption></figcaption></figure>

단, 해당 방법은 안드로이드폰에서만 지원이 되며 아이폰은 아이콘 이미지를 지정할 수 없습니다.&#x20;

푸시 아이콘 이미지 등록방법은 아래 매뉴얼 링크를 선택해주세요.&#x20;

보다 상세히 확인 가능합니다.

{% content-ref url="../../../webapp/manual/pushicon.md" %}
[pushicon.md](../../../webapp/manual/pushicon.md)
{% endcontent-ref %}



