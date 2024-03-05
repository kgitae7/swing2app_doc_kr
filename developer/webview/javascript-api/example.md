---
description: API 코드를 활용하여 앱내 서비스를 활용한 예제
---

# API 를 활용한 예제

### • 첫앱 실행 광고 허용을 팝업 노출 예시 <a href="#adpopup-permission" id="adpopup-permission"></a>

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

