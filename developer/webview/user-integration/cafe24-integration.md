---
description: 카페24(Cafe24) 웹사이트에 간단한 코드삽입으로 회원연동 활용 가이드
---

# 카페24(Cafe24) 웹사이트 회원 연동 가이드

나만의 카페24(Cafe24) 웹사이트에 사용자들이 로그인할 경우 스윙투앱 앱과의 상호 연동을 위해서

필요한 작업들을 소개하도록 하겠습니다.

회원연동을 완료하면 스윙투앱 콘솔에서 웹사이트의 회원을 조회할 수 있으며

연동된 회원을 통해서 웹사이트의 개별 회원에게 푸시 메시지를 발송할 수 있습니다.



## 1. 회원연동 가이드

### 1.1 카페24(Cafe24) Dashboard 이동 하기

<figure><img src="../../../.gitbook/assets/image (11) (1).png" alt=""><figcaption><p>카페24 콘솔화면</p></figcaption></figure>

### 1.2 홈화면에 Embed HTML 요소 삽입하기



<figure><img src="../../../.gitbook/assets/image (13) (1).png" alt=""><figcaption><p>카페24 콘솔화면</p></figcaption></figure>

(1) 전체화면 클릭 후 -> (2) 레이아웃 (하단 회사정보) 클릭 후&#x20;

페이지 최하단에 (3)번 영역에 아래의 코드 삽입 후 (4) 번 저장클릭

{% code title="HTML 요소 코드" lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2025_03_14_001/js/swing_app_on_web.js"></script>
<script type="text/javascript">
    document.addEventListener("DOMContentLoaded", function() {
        var sw_isLogin = false;
        var sw_userId = undefined;
        console.log('javascript console');
        if( window.swing2appLoginActivate == undefined ) {
            window.swing2appLoginActivate = function () {
                CAFE24API.getCustomerIDInfo(function(err, res) {
                    if (err) {
                        // 오류 발생시 Error 개체입니다.
                        // name, message 속성을 확인할 수 있습니다.
                        // res 개체를 통해 상세한 오류메세지 확인이 가능합니다.
                    } else {
                        // res 개체를 통해 응답 메세지를 확인할 수 있습니다.
                        console.log(JSON.stringify(res));
                        if( res.id != null && res.id.member_id != null )
                        {
                            sw_userId = res.id.member_id;
                            if (!sw_isLogin) {
                                if (swingWebViewPlugin && typeof (swingWebViewPlugin.app.login.doAppLogin) == 'function') {
                                    sw_isLogin = true;
                                    swingWebViewPlugin.app.login.doAppLogin(sw_userId, sw_userId);
                                    console.log('login success');
                                }
                            }
                        }
                        else
                        {
                            if (swingWebViewPlugin && typeof (swingWebViewPlugin.app.login.doAppLogout) == 'function') {
                                sw_isLogin = false;
                                swingWebViewPlugin.app.login.doAppLogout();
                            }
                        }
                    }
                });
            }
        }

        if( swingWebViewPlugin.app.methods.getCurrentPlatform() == 'android' ||
            swingWebViewPlugin.app.methods.getCurrentPlatform() == 'ios' )
        {
            setTimeout(function(){
                window.swing2appLoginActivate();
            },100);
        }
    })
</script>

```
{% endcode %}



### 1.3 회원연동 확인 작업

&#x20;     연동 작업을 모두 진행하셨다면 앱으로 웹사이트를 실행후 스윙투앱 콘솔화면 접속 후에

&#x20;     푸시&회원 -> 회원조회 화면에 들어가서 웹사이트 회원이 조회가 되는지 확인된다면&#x20;

&#x20;     정상적으로 연동된 것입니다.



<figure><img src="../../../.gitbook/assets/image (14) (1).png" alt=""><figcaption><p>스윙투앱 콘솔화면에서 카페24 회원 연동이 확인된 화면</p></figcaption></figure>



