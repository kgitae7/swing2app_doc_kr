---
description: WebView 모듈(웹뷰,푸시전용)을 제어할 수 있는 Javascript API
---

# Javascript 연동 API 문서

스윙투앱에서 제공하는 웹뷰와 푸시전용 프로토타입의 앱을 제어할 수 있는 javascript API 입니다.

공통적으로 아래의 js 파일을 include 하여 사용하시고 아래의 API 명세를 통해서

필요한 기능을 실행하시면 됩니다.

{% hint style="info" %}
공통 js 파일 HTML 파일에 아래의 js 파일을 포함시켜주세요
{% endhint %}

{% code overflow="wrap" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2023_01_16_001/js/swing_app_on_web.js"></script>
```
{% endcode %}

## 웹뷰 Javascript API 명세서

## 웹뷰 제어관련 Method

* ### 웹뷰 뒤로가기&#x20;

웹뷰에서 이전 페이지로 이동 웹브라우저에서 뒤로가기 기능과 동일한 동작

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.webview.back();
```
{% endcode %}

* ### 웹뷰 앞으로 가기

웹뷰에서 앞의 페이지로 이동 웹브라우저에서 앞으로가기 기능과 동일한 동작

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.webview.forward();
```
{% endcode %}

* ### 웹뷰 홈으로 이동

웹뷰에서 스윙투앱에 셋팅된 홈 페이지(설정된 초기 페이지)로 이동하는 기능

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.navigateToHome()
```
{% endcode %}



## 어플리케이션 관련 Method

* ### 플랫폼 정보 가져오기

웹상에서 플랫폼 정보를 가져오기 위한 함수

{% code lineNumbers="true" %}
```javascript
if( swingWebViewPlugin.app.methods.getCurrentPlatform() == 'android' )
{
    console.log('android');
}
else if( swingWebViewPlugin.app.methods.getCurrentPlatform() == 'ios' )
{
    console.log('ios');
}
else
{
    console.log('web browser');
}
```
{% endcode %}

* ### 버전 및 기기정보 가져오기

앱의 버전및 기기의 H/W 그리고 S/W 정보를 가져오는 함수

{% code lineNumbers="true" %}
```javascript
// android
swingWebViewPlugin.app.methods.getAppVersion(function(value){
    console.log('model : ' + value.model);
    console.log('sdk_version : ' + value.version);
    console.log('version_release : ' + value.version_release);
    console.log('manufacturer : ' + value.manufacturer);
    console.log('app_version : ' + value.appVersion);
    console.log('radio_version : ' + value.radio_version);
    console.log('package_name : ' + value.packageName);
});

// ios
swingWebViewPlugin.app.methods.getAppVersion(function(value){
    console.log('model : ' + value.model);
    console.log('name : ' + value.name);
    console.log('systemVersion : ' + value.systemVersion);
    console.log('appVersion : ' + value.appVersion);
    console.log('bundleVersion : ' + value.bundleVersion);
    console.log('bundleID : ' + value.bundleID);
});
```
{% endcode %}

* ### 앱 종료 기능

&#x20;실행중인 앱을 종료하는 명령어

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doExitApp();
```
{% endcode %}

* ### 외부 브라우저로 URL 실행하기

크롬 또는 사파리등 앱의 기본 브라우저로 특정 페이지를 열고 싶을때 아래의 함수를 이용할 수 있다.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doExternalOpen('https://www.swing2app.com');
```
{% endcode %}

* ### 내장 브라우저로 URL 실행하기

안드로이드와 iOS 자체적으로 제공하는 앱 내장 브라우저를 이용해서 실행

크롬과 사파리등을 반드시 이용해야 하는 경우 아래의 코드를 통해서 앱 내부에서 크롬과 사파리를 호출 할 수 있다.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.openBrowser('https://www.swing2app.com');
```
{% endcode %}

* ### 현재 페이지를 공유하기

현재 웹 페이지를 공유하는 기능을 위한 아래의 코드를 실행

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doShareCurrentPage();
```
{% endcode %}

* ### 지정 URL 공유하기

지정한 URL을 공유하고자 할 경우 아래와 같이 코드를 실행

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doShareWithUrl('https://www.swing2app.com');
```
{% endcode %}

* ### 어플리케이션의 알림 설정 상태를 확인하기

어플리케이션에서 푸시 알람 설정에 대한 상태를 확인하는 기능

푸시가 비활성화 되었을 경우 OS 자체적으로 푸시가 Off 되었을 경우와

앱 자체적인 설정으로 Off 가 되었을경우를 확인할 수 있다.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.isNotificationEnabled(function (result) {
    if( result == '1' ) // 푸시를 발송 할 수 있는 상태
    {
        console.log('push active');
    }
    else if( result == 'off_on_system' )    // 시스템 설정에 의한 앱 푸시 비활성화
    {
        console.log('push inactive');
    }
    else if( result == 'off_on_app' )       // 앱 설정에 의한 앱 푸시 비활성화
    {
        console.log('push inactive');
    }
});
```
{% endcode %}

Ex:) 푸시 설정에 따라 Off 설정일 경우 활성화 권장을 위한 코드예제

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.isNotificationEnabled(function (result) {
    if( result == '1' ) // 푸시를 발송 할 수 있는 상태
    {
        console.log('push active');
    }
    else if( result == 'off_on_system' )    // 시스템 설정에 의한 앱 푸시 비활성화
    {
        console.log('push inactive');
        swingWebViewPlugin.app.methods.goToNotificationSetting("system"); // 시스템 설정 Open
    }
    else if( result == 'off_on_app' )       // 앱 설정에 의한 앱 푸시 비활성화
    {
        console.log('push inactive');
        swingWebViewPlugin.app.methods.goToNotificationSetting("app");    // 앱 설정 Open
    }
});
```
{% endcode %}

* ### 알람 설정 이동하기

어플리케이션 또는 시스템의 알람설정을 이동할 수 있는 기능

(1) 어플리케이션 자체적인 알람 설정을 할 수 있는 화면으로 이동

```javascript
swingWebViewPlugin.app.methods.goToNotificationSetting('app');
```

(2) 시스템(안드로이드, iOS) 자체적인 알람 설정을 할 수 있는 화면으로 이동

```javascript
swingWebViewPlugin.app.methods.goToNotificationSetting('system');
```

##

## 애드몹 관련 Method

웹사이트에서 직접 앱내의 애드몹 광고를 관리할 수 있는 명령어 입니다.

아래의 내용을 참고하셔서 광고들을 활용해보세요.

{% hint style="info" %}
반드시 애드몹이 활성된 앱의 경우만 동작하는 명령어 입니다.
{% endhint %}

* ### 배너광고 노출하기

어플리케이션내에 애드몹 배너 광고를 노출시키는 명령

| Parameter | 설명             | 값 예시                                   |
| --------- | -------------- | -------------------------------------- |
| adId      | 배너광고 단위 아이디 입력 | ca-app-pub-3940256099942544/6300978111 |

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.admob.showBanner('ca-app-pub-3940256099942544/6300978111');
```
{% endcode %}

* ### 배너광고  종료하기

어플리케이션내에 애드몹 배너 광고를 종료시키는 명령

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.admob.closeBanner();
```
{% endcode %}

* ### 전면광고 노출하기

어플리케이션내에 애드몹 전면 광고를 노출시키는 명령

| Parameter | 설명             | 값 예시                                   |
| --------- | -------------- | -------------------------------------- |
| adId      | 전면광고 단위 아이디 입력 | ca-app-pub-3940256099942544/6300978111 |

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.admob.showInterstitialAd('ca-app-pub-3940256099942544/6300978111');
```
{% endcode %}




