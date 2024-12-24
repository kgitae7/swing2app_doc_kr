---
description: Meta SDK를 활용하는 Javascript Interface
---

# Meta SDK 활용하기

스윙투앱 웹뷰에서 Meta SDK 와 Interface 를 하기 위한 사용 가이드입니다.

아래의 코드를 활용해서 Native Meta SDK 를 활용해보세요.

{% hint style="info" %}
공통 js 파일 HTML 파일에 아래의 js 파일을 포함시켜주세요
{% endhint %}

{% code overflow="wrap" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_12_23_001/js/swing_app_on_web.js"></script>
```
{% endcode %}

### Meta SDK Native App Event 추가하기 <a href="#add-event" id="add-event"></a>

<mark style="background-color:blue;">\*js lib 2024\_12\_23\_001 버전 부터 사용 가능(24년 12월24일 오후 5시 이후 제작된 버전부터 동작)</mark>

값 없이 이벤트 기록하기

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.event.meta.addFbEvent('PageView');
```
{% endcode %}

값을 포함하여 이벤트 기록하기

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.event.meta.addFbEventWithValue('PageView', '1.25');
```
{% endcode %}

값과 파라미터를 포함하여 이벤트 기록하기

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.event.meta.addFbEventWithParams('PageView', '1.25',{
    'content_type': 'product',
    'content_id': '1234',
    'currency': 'USD'
});
```
{% endcode %}
