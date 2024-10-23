---
description: API 코드를 활용하여 앱내 서비스를 활용한 예제
---

# API 를 활용한 예제

### • 앱 최초 실행시 광고 허용을 팝업 노출 예시 <a href="#adpopup-permission" id="adpopup-permission"></a>

법령에 따라 사용자에게 광고푸시 허용 팝업을 노출 시키고 그에 따른 푸시 활성화 비 활성화 적용

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.isFirstRun(function (value) {
    if (JSON.parse(value).result) // 앱 첫 실행 여부 판단
    {
        swingWebViewPlugin.app.ui.openPopupDialog('알림','앱의 푸시 알림을 통해서 광고 및 뉴스 소식을 받아보시겠습니까?','허용','허용안함',
            function() // 허용 선택
            {
                swingWebViewPlugin.app.methods.activePush();
            },
            function () // 허용안함 선택
            {
                swingWebViewPlugin.app.methods.inactivePush();
            }
        );
    }
});
```
{% endcode %}



### • 웹사이트에서 앱 설치 유도 팝업 노출하기 <a href="#install-promotion-popup" id="install-promotion-popup"></a>

푸시전용 또는 웹앱을 적용한 웹사이트에서 앱을 다운로드할 수 있도록 유도하는 팝업 노출하기

안드로이드 또는 아이폰기기에서 브라우저에서 실행할 경우에만 노출되며 PC 환경에서는 노출되지 않습니다.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.web.showInstallPopup(
'발급된 앱 아이디',    // 앱 아이디(스윙투앱 고객센터에 문의해주세요.)
'앱에서 더 많은 정보를 확인해보세요',    // 팝업에 노출되는 메시지
'https://www.swing2app.co.kr/assets/images/logo.png',    // 아이콘 이미지
'앱으로 보기'    // 버튼명 입력,
'#1560e4',    // 버튼 배경색
'white'       // 버튼 글자색 
)
```
{% endcode %}

<figure><img src="../../../.gitbook/assets/image (58).png" alt=""><figcaption><p>팝업예시 이미지</p></figcaption></figure>

