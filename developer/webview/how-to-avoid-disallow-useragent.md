---
description: 스윙투앱에서 구글, 페이스북 로그인 보안으로 인한 문제 해결하기
---

# 웹뷰에서 구글, 페이스북 로그인 구현하기



***



안드로이드 앱 개발 중 구글 및 페이스북과 같은 플랫폼의 로그인 기능을 웹뷰에서 사용하려는 경우, 일반적으로 보안 상의 이유로 인해 구글과 페이스북이 해당 기능을 차단하는 경우가 있습니다.&#x20;

&#x20;(아래와 같은 메시지를 발견했다면 해당 이유로 차단된 경우입니다. )

<div align="left">

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt="" width="375"><figcaption><p>Google Login 웹뷰에서 차단</p></figcaption></figure>

</div>

<div align="left">

<figure><img src="../../.gitbook/assets/image (4) (2).png" alt="" width="375"><figcaption><p>Facebook Login 웹뷰에서 차단</p></figcaption></figure>

</div>

이러한 차단은 앱 사용자의 개인 정보와 계정 보안을 보호하기 위한 조치로 이해해야 합니다.&#x20;

이 글에서는 User Agent Disallow 이슈에 대해 자세히 알아보고, 이를 회피하기 위한 대안적인 접근 방식을 소개하겠습니다.



***



1.  **User Agent Disallow란 무엇인가요?**

    * User Agent는 클라이언트(웹 브라우저 또는 웹뷰)가 서버에게 자신의 속성을 알리기 위해 전송하는 HTTP 헤더입니다.
    * User Agent Disallow는 구글과 페이스북이 자체 로그인 기능을 웹뷰를 통해 사용하는 것을 막기 위해 해당 User Agent 문자열을 감지하여 차단하는 것을 의미합니다.


2.  **User Agent Disallow 이슈의 이유는 무엇인가요?**

    * 웹뷰는 모바일 앱 안에 내장된 경량화된 웹 브라우저로써, 보안상의 이유로 특정 기능을 차단하는 것이 필요합니다.
    * User Agent Disallow는 보안을 강화하기 위한 방식 중 하나로서, 웹뷰에서는 구글 및 페이스북과 같은 로그인 API를 사용하는 것을 제한하여 악용을 방지합니다.


3.  **User Agent Disallow를 회피하는 대안적인 방법은 무엇인가요?** 가장 일반적인 방법으로는 다음과 같은 접근 방식을 고려할 수 있습니다:

    **a. 외부 브라우저 열기:**

    * 사용자가 구글 로그인 또는 페이스북 로그인을 선택하면, 웹뷰에서는 외부 브라우저를 열어 해당 로그인 페이지를 표시합니다.
    * 외부 브라우저는 웹뷰와는 별개의 애플리케이션으로 간주되므로, 보안 정책에 영향을 받지 않습니다.
    * 로그인이 완료되면, 외부 브라우저는 로그인 결과를 콜백 URL을 통해 전달하고, 애플리케이션이 이를 캡처하여 처리할 수 있습니다.

    &#x20;    \* 아래의 [가이드](how-to-avoid-disallow-useragent.md#how-to-avoid-disallow)를 참고하여 개발해주세요.

    **b. Fake(가짜) UserAgent 사용하기**

    * 가짜 UserAgent 를 사용하면 구글 로그인의 경우는 해당 이슈를 회시 할 수 있다. 다만 페이스북은 회피가 불가능하다.
    * 스윙투앱에서 UserAgent 변경방법&#x20;

    &#x20;     앱 제작 -> 고급 설정 -> 앱 제작 설정 에서 아래의 두개 값 변경

<div align="left">

<figure><img src="../../.gitbook/assets/image (2) (3).png" alt="" width="563"><figcaption><p>스윙투앱에서 UserAgent 변경방법 </p></figcaption></figure>

</div>

&#x20;       (1) Android WebView UserAgent

&#x20;          \-> 구글 로그인 회피 가능한 UserAgent 값 (Android)

&#x20;          <mark style="color:blue;">**"Mozilla/5.0 (Linux; Android 9; SM-G950N) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/88.0.4324.93 Mobile Safari/537.36"**</mark>

&#x20;       (2) IOS WebView UserAgent

&#x20;          \-> 구글 로그인 회피 가능한 UserAgent 값 (iOS)

&#x20;          <mark style="color:blue;">**"Mozilla/5.0 (iPhone; CPU iPhone OS 16\_0 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/16.0 Mobile/15E148 Safari/604.1"**</mark>



***



## 외부 브라우저 열기 방법으로 구글 및 페이스북 로그인 회피하는 방법 알아보기 <a href="#how-to-avoid-disallow" id="how-to-avoid-disallow"></a>

### #실행 프로세스&#x20;

(1) 웹뷰에서 login\_example.html 을 앱 내 내장 브라우저로 실행한다

login\_example.html 실행 예제 코드를 아래에 첨부되었습니다.

login\_example.html 실행 파라미터중 customUrl 항목이 있는데 해당 항목은 고급설정에서 설정하실 수 있습니다. 설정된 값을 사용하셔도 됩니다.

\*custom url scheme 값은 앱 마다 고유값으로 설정하는 것을 권장드립니다.

<div align="left">

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt="" width="563"><figcaption><p>custom scheme 확인 및 설정하는 화면</p></figcaption></figure>

</div>

{% code title="실행코드" %}
```javascript
swingWebViewPlugin.app.methods.openBrowser('https://www.swing2app.co.kr/sns_login_temp/sns_login_temp_ext.html?customUrl=myapp1706');
```
{% endcode %}

* 자세한 브라우저 실행 API 는 아래의 Javascript 연동 API를 참고하세요.

{% content-ref url="javascript-api.md" %}
[javascript-api.md](javascript-api.md)
{% endcontent-ref %}

아래의 코드를 활용하여 로그인 페이지를 만들어주세요.

* 아래의 코드에서 todo 에 기재된 facebook 앱 아이디와 구글 client id 는 반드시 변경후에 사용해야 합니다.

{% code title="" fullWidth="false" %}
```html
<html>
<head>
    <!-- Title -->
    <title>Swing-test</title>
    <meta content="width=device-width, initial-scale=1" name="viewport">
    <meta charset="UTF-8">
    <!-- Javascripts -->
    <script src="/assets/plugins/jquery/jquery-2.1.4.min.js"></script>
    <script>
        var host = location.host.toLowerCase();
        const urlParams = new URLSearchParams(window.location.search);
        var customUrl = urlParams.get('customUrl');
        var autoType = urlParams.get('autoType');
        $(document).ready(function () {
            window.fbAsyncInit = function() {
                FB.init({
                    appId      : '464485827223968', // todo facebook 앱 아이디를 입력
                    xfbml      : true,
                    version    : 'v9.0'
                });
                FB.AppEvents.logPageView();

                if( autoType == "facebook"){
                    fb_login();
                }
            };

            (function(d, s, id){
                var js, fjs = d.getElementsByTagName(s)[0];
                if (d.getElementById(id)) {return;}
                js = d.createElement(s); js.id = id;
                js.src = "https://connect.facebook.net/en_US/sdk.js";
                fjs.parentNode.insertBefore(js, fjs);
            }(document, 'script', 'facebook-jssdk'));
        });

        var googleAuth2 = null;
        function fb_login(){
            $("#infoBox").append("fb_login start");

            FB.login(function(response) {
                if (response.authResponse) {
                    console.log('Welcome!  Fetching your information.... ');
                    var access_token = response.authResponse.accessToken; //get access token
                    if (response.status === 'connected') {   // Logged into your webpage and Facebook.
                        gotoSnsLoginPageFn("facebook", access_token);
                    } else {

                    }
                } else {
                    //user hit cancel button
                    console.log('User cancelled login or did not fully authorize.');
                }
            }, {
                scope: 'public_profile,email'
            });
        }

        function googleInitFn() {
            gapi.load('auth2', function() {
                /* Ready. Make a call to gapi.auth2.init or some other API */
                googleAuth2 = gapi.auth2.init({
                    client_id: '829822048277-oncammdmeq2mku9lbqndknoustamqcbq.apps.googleusercontent.com',  // todo google client_id 입력
                    cookiepolicy: 'single_host_origin',
                    scope: 'profile email'
                });
                attachSignin(document.getElementById('googleLoginBtn'));

                if( autoType == "google" ) {
                    setTimeout(function() {
                        $("#googleLoginBtn")[0].click();
                    },1000);
                }

            });
        }
        function attachSignin(element) {
            console.log(element.id);
            googleAuth2.attachClickHandler(element, {},
                function(googleUser) {
                    var loginAuth2 = gapi.auth2.getAuthInstance();
                    if (loginAuth2.isSignedIn.get()) {
                        var authToken = loginAuth2.currentUser.get().getAuthResponse().id_token;
                        gotoSnsLoginPageFn("google", authToken);
                    }

                }, function(error) {
                    // alert(JSON.stringify(error, undefined, 2));
                });
        }

        function googleLoginActionFn(){
            googleAuth2.signIn().then(function(user){
                if (user.isSignedIn()) {
                    var authToken = user.getAuthResponse().id_token;
                    gotoSnsLoginPageFn("google", authToken);
                }
            });
        }

        function gotoSnsLoginPageFn(idType, token){
            var $form = $("#snsLoginForm");
            $form.find("[name=id_type]").val(idType);
            $form.find("[name=token]").val(token);

            var runUrl = customUrl +'://app?function=command&linkUrl=' + btoa( "loginTokenCallback('"+ token +"','" + idType + "');" );
            $('.return-app-area a').attr('href', runUrl );
            $('.sns-login-area').hide();
            $('.return-app-area').show();


            if( location.href.indexOf('swing2app.com') >= 0 )
            {
                $('.command-button').text('Login successful - Proceed');
            }
            else {
                $('.command-button').text('로그인 성공 - 이동하기');
            }
        }

    </script>

    <meta name="google-signin-client_id" content="829822048277-oncammdmeq2mku9lbqndknoustamqcbq.apps.googleusercontent.com">    <!-- todo google signin-client-id 입력 -->
    <script src="https://apis.google.com/js/platform.js?onload=googleInitFn" async defer></script>

    <script>
    </script>
</head>
<body>

<div class="sns-login-area" style="width: 100%; padding:30px">
    <div class="sns-login-btn-box facebook">
        <div class="sns-login-main-btn" id="snsFaceBookLoginBtn" onclick="fb_login();">
            <span class="icon"><img src="/assets/images/sns_login/facebook.png" /></span>
            <span class="buttonText">페이스북으로 로그인</span>
        </div>
    </div>

    <div class="sns-login-btn-box google">
        <div id="googleLoginBtn" class="customGPlusSignIn sns-login-main-btn">
            <span class="icon"><img src="/assets/images/sns_login/google.png" /></span>
            <span class="buttonText">구글로 로그인</span>
        </div>
    </div>
</div>

<div class="return-app-area" style="display: none;padding: 30px;text-align: center;background: #e6e6e6;"><a href="#" class="command-button" style="color: black;text-decoration: none;font-size: 25px;">로그인 성공 - 이동하기</a>
</div>
<div id="infoBox" style="display: none">
</div>

</body>
</html>

```
{% endcode %}

(2) 웹사이트에서 callback 함수를 정의하여 device token 을 받기

1번 브라우저에서 로그인이 완료되면 아래의 정의된 callback 함수로 deviceToken 이 전달된다, idType 값은 login\_example.html 정의된 값으로 전달되는데 제공되는 소스에서는 "facebook", "google"로 구분되어 들어오게 되어있다.



{% code title="사이트내 callback 구현" %}
```javascript
function loginTokenCallback(token, idType) {
    console.log("token : " + token );
    console.log("idType : " + idType );
}
```
{% endcode %}

(3) 전달받은 accessToken 으로 로그인 구현하기

이후에는 전달받은 accessToken 으로 웹사이트내에서 사용자 정보를 가져와 연동 로그인을 구현해주면 된다.

