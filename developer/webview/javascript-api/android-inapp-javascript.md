---
description: 스윙투앱 WebView 모듈(푸시전용)에 인앱결제 모듈을 Javascript API 로 구현하기
---

# 안드로이드 인앱결제 구현하기



스윙투앱에서 제공하는 웹뷰와 푸시전용 프로토타입의 앱을 제어할 수 있는 javascript API 입니다.

공통적으로 아래의 js 파일을 include 하여 사용하시고 아래의 API 명세를 통해서

필요한 기능을 실행하시면 됩니다.

{% hint style="info" %}
공통 js 파일 HTML 파일에 아래의 js 파일을 포함시켜주세요
{% endhint %}

{% code overflow="wrap" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2025_02_14_001/js/swing_app_on_web.js"></script>
```
{% endcode %}



## 안드로이드 인앱결제 구현

### 결제방식별 인앱 결제 구현하기

### (1) 소모성 상품 인앱 결제 구현 예제

소모성 상품은 사용자가 구매한 후 소모되는 형태의 아이템을 의미합니다. 예를 들어, 게임에서 사용하는 코인이나 추가 생명, 비디오 스트리밍 서비스에서 사용할 수 있는 일회성 영상 시청권 등이 소모성 상품에 해당합니다.

#### 구글 플레이 스토어의 소모성 상품

구글 플레이 스토어에서 소모성 상품은 사용자가 구매한 후 일정량 소모되거나 사라지는 디지털 콘텐츠입니다. 이러한 상품은 구매 후 즉시 사용 가능하며, 사용자가 재구매할 수 있습니다.

(예: 게임 아이템, 충전 포인트 등)

#### 구현 예제

구현을 시작하기 전에, 구글 플레이 콘솔에서 소모성 상품을 생성하고, 해당 상품 ID를 준비합니다. 아래는 소모성 상품 결제를 스윙투앱 모듈에서 구현하는 코드의 예시입니다:

```javascript
var productId = 'test_product_id';
swingWebViewPlugin.app.inapp.buy(productId,
    function(responseCode,data) {
        console.log('responseCode : ' + responseCode + ', ret : ' + JSON.stringify(data));
        if( responseCode == 0 ) // 결제성공
        {
            // 값 예시(data)
            // [{
            //     "orderId": "GPA.3355-4848-8386-49751",
            //     "packageName": "com.hustay.swing.dededae603d0b4850bac7d4209309ce94",
            //     "productId": "testpd1",
            //     "purchaseTime": 1668091465146,
            //     "purchaseState": 0,
            //     "purchaseToken": "oljaodejfekfnhiddnefhmen.AO-J1OyIDgeuh3_XLdbmMaptYo81FidgEn3_n3zozmMfj4DqOn51RXY5U_XSeFOpDO4UplBiKsc59SVoPQjcp-jVTllJK_3P2ZMsPdzzBouc14jXN7DVLAg7tOFvKLjQ--HfGzIHpgKB",
            //     "quantity": 1,
            //     "acknowledged": false
            // }]

            console.log('originalData : ' + data );
            
            data = JSON.parse(data);
            var purchaseToken = data[0].purchaseToken;
            var productId = data[0].productId;

            console.log('purchaseToken : ' + purchaseToken );
            console.log('productId : ' + productId );
        }
        else if( responseCode == 1 )    // 취소
        {
            console.log('사용자 취소');
            // todo ( 사용자가 취소한 경우 처리하시면 됩니다. )
        }
        else    // 기타 에러
        {
            console.log('기타 에러 에러코드 : ' + responseCode );
            // int SERVICE_TIMEOUT = -3;
            // int FEATURE_NOT_SUPPORTED = -2;
            // int SERVICE_DISCONNECTED = -1;
            // int SERVICE_UNAVAILABLE = 2;
            // int BILLING_UNAVAILABLE = 3;
            // int ITEM_UNAVAILABLE = 4;
            // int DEVELOPER_ERROR = 5;
            // int ERROR = 6;
            // int ITEM_ALREADY_OWNED = 7;
            // int ITEM_NOT_OWNED = 8;

            // todo ( 위의 에러 코드에 맞게 처리하시면 됩니다. )

        }
    })
```

이 코드는 사용자가 제품을 구매하려고 할 때 결제 API를 호출하고, 결제 성공 시 영수증을 처리하는 과정을 보여줍니다. 각 단계에서 발생할 수 있는 오류를 처리하여 사용자 경험을 향상시키는 것이 중요합니다.



### (2) 비소모성 상품 인앱 결제 구현 예제

비소모성 상품은 사용자가 구매한 후 소유하는 형태의 아이템을 의미합니다. 예를 들어,  디지털 컨텐츠 구매, 영화 구매, PDF 구매 등의 한번 구매후 소유권을 갖게되는 상품을 의미합니다.

#### 구글 플레이 스토어의 비소모성 상품

비소모성 상품은 한 번 구매하면 영구적으로 사용 가능한 상품을 말합니다. 예를 들어, 광고 제거 기능이나 특정 기능의 영구적인 해제 등이 해당됩니다. 비소모성 상품은 반복 구매가 불가능하여, 구매 완료 상태를 사용자 계정에 저장하고 관리해야 합니다.

(예: 유료 컨텐츠 구매, 영화 다운로드 등)

#### 구현 예제

구현을 시작하기 전에, 구글 플레이 콘솔에서 비소모성 상품을 생성하고, 해당 상품 ID를 준비합니다. 아래는 비소모성 상품 결제를 스윙투앱 모듈에서 구현하는 코드의 예시입니다:

```javascript
var productId = 'test_product_id';
swingWebViewPlugin.app.inapp.buyAndType(productId,'none-consume',
    function(responseCode,data) {
        console.log('responseCode : ' + responseCode + ', ret : ' + JSON.stringify(data));
        if( responseCode == 0 ) // 결제성공
        {
            // 값 예시(data)
            // [{
            //     "orderId": "GPA.3355-4848-8386-49751",
            //     "packageName": "com.hustay.swing.dededae603d0b4850bac7d4209309ce94",
            //     "productId": "testpd1",
            //     "purchaseTime": 1668091465146,
            //     "purchaseState": 0,
            //     "purchaseToken": "oljaodejfekfnhiddnefhmen.AO-J1OyIDgeuh3_XLdbmMaptYo81FidgEn3_n3zozmMfj4DqOn51RXY5U_XSeFOpDO4UplBiKsc59SVoPQjcp-jVTllJK_3P2ZMsPdzzBouc14jXN7DVLAg7tOFvKLjQ--HfGzIHpgKB",
            //     "quantity": 1,
            //     "acknowledged": false
            // }]

            console.log('originalData : ' + data );
            
            data = JSON.parse(data);
            var purchaseToken = data[0].purchaseToken;
            var productId = data[0].productId;

            console.log('purchaseToken : ' + purchaseToken );
            console.log('productId : ' + productId );
        }
        else if( responseCode == 1 )    // 취소
        {
            console.log('사용자 취소');
            // todo ( 사용자가 취소한 경우 처리하시면 됩니다. )
        }
        else    // 기타 에러
        {
            console.log('기타 에러 에러코드 : ' + responseCode );
            // int SERVICE_TIMEOUT = -3;
            // int FEATURE_NOT_SUPPORTED = -2;
            // int SERVICE_DISCONNECTED = -1;
            // int SERVICE_UNAVAILABLE = 2;
            // int BILLING_UNAVAILABLE = 3;
            // int ITEM_UNAVAILABLE = 4;
            // int DEVELOPER_ERROR = 5;
            // int ERROR = 6;
            // int ITEM_ALREADY_OWNED = 7;
            // int ITEM_NOT_OWNED = 8;

            // todo ( 위의 에러 코드에 맞게 처리하시면 됩니다. )

        }
    })
```

이 코드는 사용자가 제품을 구매하려고 할 때 결제 API를 호출하고, 결제 성공 시 영수증을 처리하는 과정을 보여줍니다. 각 단계에서 발생할 수 있는 오류를 처리하여 사용자 경험을 향상시키는 것이 중요합니다.



### 구글 플레이 스토어 인앱 결제 구독 상품 설명

구글 플레이 스토어의 인앱 결제 구독은 사용자가 특정 기간 동안 지속적으로 서비스를 사용할 수 있도록 하는 결제 모델입니다. 구독 상품은 주로 정기적인 콘텐츠 업데이트가 있는 앱에서 활용됩니다. 구독 모델은 고객 유지율을 높이고, 안정적인 수익 창출을 도와줍니다.

#### 구독 상품 예제 코드

구독 상품 결제를 처리할 때 아래와 같은 예제를 참고할 수 있습니다:

```javascript
var productId = 'test_product_id';
swingWebViewPlugin.app.inapp.subscribe(productId,
    function(responseCode,data) {
        console.log('responseCode : ' + responseCode + ', ret : ' + JSON.stringify(data));
        if( responseCode == 0 ) // 성공
        {
            // 값 예시(data)
            // [{
            //     "orderId": "GPA.3355-4848-8386-49751",
            //     "packageName": "com.hustay.swing.dededae603d0b4850bac7d4209309ce94",
            //     "productId": "testpd1",
            //     "purchaseTime": 1668091465146,
            //     "purchaseState": 0,
            //     "purchaseToken": "oljaodejfekfnhiddnefhmen.AO-J1OyIDgeuh3_XLdbmMaptYo81FidgEn3_n3zozmMfj4DqOn51RXY5U_XSeFOpDO4UplBiKsc59SVoPQjcp-jVTllJK_3P2ZMsPdzzBouc14jXN7DVLAg7tOFvKLjQ--HfGzIHpgKB",
            //     "quantity": 1,
            //     "acknowledged": false
            // }]

            console.log('originalData : ' + data );
            
            data = JSON.parse(data);
            var purchaseToken = data[0].purchaseToken;
            var productId = data[0].productId;

            console.log('purchaseToken : ' + purchaseToken );
            console.log('productId : ' + productId );


            // 구독 상품은 결제 성공이후 API 호출을 통해 서버에 구매 확정 요청을 반드시 보내야 한다.
            // 구매확정을 하지 않을 경우 일정시간이후 구독이 취소됩니다.
            // 구매확정 backend 구현은 아래의 API 를 참고하시면 됩니다.
            // purchaseToken 을 이용해서 향후에도 유효한 구매인지 확인할 수 있다.
            // https://developers.google.com/android-publisher/api-ref/rest/v3/purchases.subscriptions/acknowledge
            // API의 subscriptionId 파라미터는 productId와 같은 값이다.
        }
        else if( responseCode == 1 )    // 취소
        {
            console.log('사용자 취소');
            // todo ( 사용자가 취소한 경우 처리하시면 됩니다. )
        }
        else    // 기타 에러
        {
            console.log('기타 에러 에러코드 : ' + responseCode );
            // int SERVICE_TIMEOUT = -3;
            // int FEATURE_NOT_SUPPORTED = -2;
            // int SERVICE_DISCONNECTED = -1;
            // int SERVICE_UNAVAILABLE = 2;
            // int BILLING_UNAVAILABLE = 3;
            // int ITEM_UNAVAILABLE = 4;
            // int DEVELOPER_ERROR = 5;
            // int ERROR = 6;
            // int ITEM_ALREADY_OWNED = 7;
            // int ITEM_NOT_OWNED = 8;

            // todo ( 위의 에러 코드에 맞게 처리하시면 됩니다. )

        }
    });
```

위의 코드에서는 사용자가 구독을 구매하려고 할 때 결제 API를 호출하고, 결제가 성공적으로 완료되면 관련 데이터를 처리합니다. 구독 상태를 지속적으로 확인하고 갱신하여 사용자가 콘텐츠를 지장 없이 사용할 수 있도록 보장합니다.

## &#x20;

