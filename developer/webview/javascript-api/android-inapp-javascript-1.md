---
description: 스윙투앱 WebView 모듈(푸시전용)에 인앱결제 모듈을 Javascript API 로 구현하기
---

# iOS 인앱결제 구현하기



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



## iOS 인앱결제 구현

### 결제방식별 인앱 결제 구현하기

### (1) 비구독 상품 인앱 결제 구현 예제

비구독 상품은 소모성과 비소모성 상품으로 구분됩니다. 소모성 상품과 비구독상품은 앱스토어 코넥트에서 상품을 등록할때 설정을 통해서 등록이 가능합니다.&#x20;

#### 앱스토어의 소모성 상품

앱스토어에서 소모성 상품은 사용자가 구매한 후 일정량 소모되거나 사라지는 디지털 콘텐츠입니다. 이러한 상품은 구매 후 즉시 사용 가능하며, 사용자가 재구매할 수 있습니다.

(예: 게임 아이템, 충전 포인트 등)

#### 앱스토어의 비소모성 상품

비소모성 상품은 한 번 구매하면 영구적으로 사용 가능한 상품을 말합니다. 예를 들어, 광고 제거 기능이나 특정 기능의 영구적인 해제 등이 해당됩니다. 비소모성 상품은 반복 구매가 불가능하여, 구매 완료 상태를 사용자 계정에 저장하고 관리해야 합니다.

(예: 유료 컨텐츠 구매, 영화 다운로드 등)

#### 구현 예제

구현을 시작하기 전에, 앱스토어 콘솔에서 소모성 상품 또는 비소모성 상품을 생성하고, 해당 상품 ID를 준비합니다. 아래는 비구독상품 결제를 스윙투앱 모듈에서 구현하는 코드의 예시입니다:

```javascript
var productId = 'test_product_id';
swingWebViewPlugin.app.inapp.buy(productId,
    function(responseCode,data) {
        console.log('responseCode : ' + responseCode + ', ret : ' + JSON.stringify(data));
        if( responseCode == 1 ) // 성공
        {
            console.log('originalData : ' + data );                                            
            // 값 예시
            // responseCode : 1, ret : "{\"transaction\":{\"transactionIdentifier\":\"2000000524327453\"},\"productId\":\"swbwregsubweek\",\"needsFinishTransaction\":false,\"originalTransaction\":{\"transactionIdentifier\":null},\"receipt\":\"=test=\",\"quantity\":1}"
            data = JSON.parse(data);
            var receipt = data.receipt;
            var productId = data.productId;
            var transactionIdentifier = data.transaction.transactionIdentifier;

            // ajax 호출을 통해 서버에 transaction 정보를 확인해보세요.
            // 유효한 구독 상품인지 확인을 위해 아래의 함수를 호출합니다.
            // 구독 상태 정보 backend 구현은 아래의 API 를 참고하시면 됩니다.
            // https://developer.apple.com/documentation/appstoreserverapi/get_all_subscription_statuses
            console.log('receipt : ' + receipt );
            console.log('transactionId : ' + transactionIdentifier );
            console.log('productId : ' + productId );

        }
        else    // 기타 에러
        {
            console.log('error code : ' + responseCode );
        }

    })
```

이 코드는 사용자가 제품을 구매하려고 할 때 결제 API를 호출하고, 결제 성공 시 영수증을 처리하는 과정을 보여줍니다. 각 단계에서 발생할 수 있는 오류를 처리하여 사용자 경험을 향상시키는 것이 중요합니다.



### 앱스토어 인앱 결제 구독 상품 설명

앱스토어의 인앱 결제 구독은 사용자가 특정 기간 동안 지속적으로 서비스를 사용할 수 있도록 하는 결제 모델입니다. 구독 상품은 주로 정기적인 콘텐츠 업데이트가 있는 앱에서 활용됩니다. 구독 모델은 고객 유지율을 높이고, 안정적인 수익 창출을 도와줍니다.

#### 구독 상품 예제 코드

구독 상품 결제를 처리할 때 아래와 같은 예제를 참고할 수 있습니다:

```javascript
var productId = 'test_product_id';
swingWebViewPlugin.app.inapp.subscribe(productId,
    function(responseCode,data) {
        console.log('responseCode : ' + responseCode + ', ret : ' + JSON.stringify(data));
        if( responseCode == 1 ) // 성공
        {
            console.log('originalData : ' + data );    
            // 값 예시
            // responseCode : 1, ret : "{\"transaction\":{\"transactionIdentifier\":\"2000000524327453\"},\"productId\":\"swbwregsubweek\",\"needsFinishTransaction\":false,\"originalTransaction\":{\"transactionIdentifier\":null},\"receipt\":\"=test=\",\"quantity\":1}"
            data = JSON.parse(data);
            var receipt = data.receipt;
            var productId = data.productId;
            var transactionIdentifier = data.transaction.transactionIdentifier;

            console.log('receipt : ' + receipt );
            console.log('transactionId : ' + transactionIdentifier );
            console.log('productId : ' + productId );
            
            // ajax 호출을 통해 서버에 transaction 정보를 확인해보세요.
            // 유효한 구독 상품인지 확인을 위해 아래의 함수를 호출합니다.
            // 구독 상태 정보 backend 구현은 아래의 API 를 참고하시면 됩니다.
            // https://developer.apple.com/documentation/appstoreserverapi/get_all_subscription_statuses
        }
        else    // 기타 에러
        {
            var errorCode = responseCode;
            var errorMsg = data;
            console.log('error msg : ' + errorMsg );
            //  errorCode list
            //  Unknown error. Please contact support = 0;
            //  Not allowed to make the payment = 1 or 3;
            //  The device is not allowed to make the payment = 4;
            //  The product is not available in the current storefront = 5;
            //  Access to cloud service information is not allowed = 6;
            //  Could not connect to the network = 7;
            //  User has revoked permission to use this cloud service = 8;
        }

    })
```

위의 코드에서는 사용자가 구독을 구매하려고 할 때 결제 API를 호출하고, 결제가 성공적으로 완료되면 관련 데이터를 처리합니다. 구독 상태를 지속적으로 확인하고 갱신하여 사용자가 콘텐츠를 지장 없이 사용할 수 있도록 보장합니다.

## &#x20;

