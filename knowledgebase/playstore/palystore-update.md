---
description: 앱 버전 새로 올리기, 스토어 등록정보, 앱 컨텐츠를 업데이트 하는 방법
---

# 플레이스토어 앱 업데이트

<figure><img src="../../.gitbook/assets/구분선 (1) (2).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2020/04/%EB%8B%A8%EB%9D%BD1-e1611212616323.png) STEP1. 새 버전의 AAB파일 업데이트

\*구글 플레이 콘솔: [https://play.google.com/console/developers](https://play.google.com/console/developers)

앱 버전이 업데이트 된 경우, 새 버전의 AAB파일을 다운받아서 플레이스토어- 프로덕션에 올려주시면 됩니다.

**AAB파일만 새로 올려주시면 되기 때문에 간단하구요.**

플레이스토어에서 새 버전의 앱으로 업데이트 하는 방법을 알려드릴게요.

{% hint style="danger" %}
<mark style="color:red;">**주의사항**</mark>

AAB파일로 출시된 앱이 아닌 **APK파일로 출시된 앱이라면 → 업데이트시에도 APK파일로 올려주셔야 합니다.**

플레이스토어 업데이트를 하는 경우, 기존 APK파일로 출시된 앱은 AAB파일이 아닌 APK파일로 올려주시면 됩니다.&#x20;

일반 프로토타입 앱, 푸시/웹뷰 앱 모두 동일합니다. **APK파일로 등록되어 출시된 앱은 업데이트를 할 경우도 APK파일을 올려주세요.**&#x20;

AAB파일로 등록 및 출시 후 업데이트를 한다면 **→** AAB파일로 올려주시면 됩니다.&#x20;

즉, 파일 확장자를 동일하게 맞춰서 업데이트 해주셔야 합니다.
{% endhint %}

{% hint style="info" %}
**앱 버전 업데이트? 어떤 경우에 AAB파일을 업데이트 해야 하나요?**

<mark style="color:blue;">**\*1단계 앱 기본정보- 앱이름, 대기화면 이미지, 앱 아이콘 이미지 변경**</mark>&#x20;

<mark style="color:blue;">**\*2단계 디자인테마 – 프로토타입 UI변경, 스킨 컬러 변경**</mark>

위의 2가지 단계 내용을 수정하게 되면 저장 후 \[앱제작하기]를 선택해서 새 버전으로 앱제작(업데이트)을 해주셔야 합니다.

이렇게 새 버전으로 앱제작이 완료되면, 플레이스토어 프로덕션에서 새버전의 앱을 올려서 업데이트 해야 합니다. AAB파일 업데이트 필수!!

<mark style="color:blue;">\*3단계 페이지 메뉴는 내용 입력 후 저장만 하면 앱 자동 반영되오니 제작 다시 할 필요 없고 업데이트 하실 필요 없습니다.</mark>
{% endhint %}





### <mark style="color:blue;">**1.구글 플레이 콘솔 접속 – 업데이트 할 앱 선택하기**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B86new.png)

구글 플레이 콘솔사이트에 접속 [**https://play.google.com/console/developers**](https://play.google.com/console/developers)→ 업데이트 할 어플을 선택해주세요.

&#x20;<mark style="color:red;">\*구글 플레이 콘솔은 인터넷 브라우저 Chrome 으로 이용해주세요.</mark>&#x20;



### <mark style="color:blue;">**2.프로덕션 → 새 버전 만들기**</mark>&#x20;

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B81.png)

**콘솔 사이트 왼쪽 메뉴 **<mark style="color:green;">**1) \[프로덕션] 선택 → 2)\[새 버전 만들기]**</mark>** 버튼을 선택합니다.**&#x20;



### <mark style="color:blue;">**3.프로덕션 버전 만들기 – AAB파일 \[업로드] 하기**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B87new.png)

프로덕션 버전 만들기 페이지에서 \[업로드] 버튼을 선택해서 새로운 버전의 AAB파일을 등록해주세요.

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%99%94%EC%82%B4%ED%91%9C-3.png)

<mark style="color:red;">**\*AAB파일은 어디서 다운받나요??**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/aab%ED%8C%8C%EC%9D%BC%EB%8B%A4%EC%9A%B41.png)

앱제작이 완료된 후 앱운영- 버전관리 – 앱제작이력 페이지로 이동합니다.

여기서 \[AAB파일 받기] 버튼을 선택하면 사용자의 PC로 파일이 다운되요.

다운된 AAB파일을 위의 구글 플레이 – 프로덕션 – App Bundle 파일로 업로드 해주시면 됩니다.

<mark style="color:red;">\*인터넷 브라우저 Chrome으로 이용해주세요.</mark>&#x20;

{% hint style="info" %}
<mark style="color:blue;">**\*중요안내**</mark>

플레이스토어 앱 등록 시스템 업데이트로 기존 앱 등록 파일인 APK파일에서 → AAB파일로 변경되었습니다.

**AAB파일은 스윙투앱에서 21년 8월9일 이후에 제작된 앱부터 생성이 됩니다.​**

따라서 21.08.09 이전에 제작된 앱은 앱제작으로 이동하셔서 \[앱 업데이트]버튼 선택하여 새 버전으로 앱제작 다시 해주세요.

새로 제작된 앱부터 AAB파일을 받을 수 있습니다.

만약 정상적으로 등록이 되지 않는다면 스윙투앱 문의게시판으로 문의 남겨주시기 바랍니다.
{% endhint %}

{% hint style="success" %}
<mark style="color:green;">**TIP. 파일 드래그하여 등록하기**</mark>

구글 플레이 콘솔 화면과 / 스윙투앱 사이트 2개 화면을 열어놓구요.

스윙투앱 사이트에서 받은 AAB파일을 마우스로 끌어서(드래그하여)  플레이 콘솔 화면의 앱 파일로 등록할 수 있어요.&#x20;

따로 파일을 저장하여 불러오는 것보다 보다 편하게 작업 하실 수 있겠죠?^^
{% endhint %}

### &#x20;<mark style="color:blue;">4.AAB파일 업로드 완료</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B82-1.png)

AAB파일을 다 올리면 하단의 저장 , 검토버튼이 활성화됩니다.

<mark style="color:blue;">**1)저장 → 2)버전검토 선택**</mark>&#x20;

<mark style="color:red;">\*’이번 버전의 새로운 기능(출시노트)’은 새로 업데이트 된 내용을 작성하는 칸입니다.</mark>&#x20;

<mark style="color:red;">(필수 입력 항목은 아닙니다)</mark>

이전에 출시된 내용과 동일할 경우 \[이전 버전에서 복사] 버튼을 눌러주세요.&#x20;

이전에 작성한 글이 그대로 등록됩니다.&#x20;



![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B83.png)

AAB파일 저장이 완료되면, 다시 하단에 \[프로덕션 트랙으로 출시 시작] 버튼이 생성됩니다.&#x20;

<mark style="color:blue;">**\[프로덕션 트랙으로 출시 시작]**</mark>버튼을 선택하면 완료됩니다.&#x20;



<mark style="color:red;">**★잠깐!**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EA%B2%BD%EA%B3%A02.jpg)

프로덕션 출시전 경고 메시지가 뜰 수 있어요.

권장 메시지이기 때문에 해당 메시지는 무시하고 넘어가시면 됩니다. (출시에는 아무 영향을 주지 않아요!)



### <mark style="color:blue;">**5.업데이트 검토 중**</mark>&#x20;

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B82new.png)

업데이트 검토 중 단계를 확인할 수 있습니다.

이렇게 하면, AAB파일 (앱) 업데이트 과정은 모두 완료되구요.

<mark style="color:red;">\*업데이트도, 앱 출시와 동일하게 심사 시간이 있어요.</mark>&#x20;

<mark style="color:red;">(보통 하루 이내로 완료되지만, 최대 7일까지 심사가 걸릴 경우도 있습니다.)</mark>

\-심사가 완료되면 업데이트된 버전으로 다시 출시가 됩니다.

\-업데이트 심사에서 심사가 거절될 수도 있기 때문에 거절 될 경우 내용을 확인하여 다시 재심사 진행해야 합니다.



### <mark style="color:blue;">**6.업데이트 완료**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B811new.png)

업데이트가 완료되면, 출시 개요 페이지에서 프로덕션 전체출시를 확인할 수 있습니다.&#x20;

만약 ‘업데이트 거절됨’, ‘업데이트 거부됨’, ‘앱 삭제’ 등의 메시지가 뜰 경우 심사가 거절된 것이구요.

구글에서 받은 거절 메일 확인하셔서 조치사항대로 처리해주셔야 합니다.&#x20;

<figure><img src="../../.gitbook/assets/구분선 (1) (2).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2020/04/%EB%8B%A8%EB%9D%BD1-e1611212616323.png) STEP2. 스토어 등록정보 수정하여 업데이트하기

이어서 스토어 등록정보를 수정하여 업데이트 하는 방법을 알려드릴거에요!!

플레이스토어에서 보여지는 **앱 이름, 간단한설명, 자세한 설명, 스크린샷 이미지를 변경하고 싶을 경우는**?

동일하게 **\*구글 콘솔–스토어등록정보 페이지에서 내용을 수정하고 업데이트하면 스토어에 반영이 됩니다.**

### &#x20;<mark style="color:blue;">**1.앱 정보 → 기본 스토어 등록정보**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B83new.png)

**구글 플레이 콘솔사이트에 접속** [**https://play.google.com/console** ](https://play.google.com/console) **→ 업데이트 할 어플을 선택해주세요.**

**앱 선택한 상태에서 왼쪽 메뉴 \[앱 정보]에서 \[스토어 등록정보] 페이지로 이동합니다.**

스토어에서 내용을 수정하고 업데이트 하는 방법은 더 간단해요!

스토어 등록정보에서 처음 앱 출시를 할때 등록했던 내용을 직접 수정해주시면 됩니다.

\=> 스토어 등록정보는 <mark style="color:green;">출시 앱이름, 간단한/자세한 설명, 스크린샷 이미지, 아이콘 이미지, 그래픽 이미지, 이메일주소</mark> 등을 수정할 수 있습니다.&#x20;



### <mark style="color:blue;">**2.수정 후 \[저장] 버튼 선택**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B84new.png)

수정을 하면 화면 하단에 안보였던 <mark style="color:blue;">**\[저장]**</mark>** 버튼**이 파란색으로 바뀌면서 활성화됩니다.

해당 버튼을 누르면 업데이트가 진행됩니다.

<mark style="color:red;">**\*스토어 등록정보 수정도 업데이트 심사 후 반영이 됩니다.**</mark>&#x20;

업데이트는 평균 1일 이지만, 심사에 따라 최대 7일까지 걸리는 경우가 있어서 편차가 좀 큽니다 ㅜㅜ

심사가 완료되면 업데이트된 버전으로 스토어 정보가 바뀌게 됩니다.

<figure><img src="../../.gitbook/assets/구분선 (1) (2).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2020/04/%EB%8B%A8%EB%9D%BD1-e1611212616323.png) STEP3. 스토어 설정

앱 카테고리, 연락처 수정은 스토어 설정에서 수정 가능합니다.&#x20;

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B810new.png)

**앱 정보 →스토어 설정 으로 이동, 내용 수정 후 \[저장]버튼을 눌러주세요.**

<mark style="color:red;">**\*스토어 설정 수정도 업데이트 심사 후 반영이 됩니다.**</mark>&#x20;

<figure><img src="../../.gitbook/assets/구분선 (1) (2).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2020/04/%EB%8B%A8%EB%9D%BD1-e1611212616323.png) STEP4. 앱 콘텐츠 수정&#x20;

개인정보 처리방침 링크 수정, 광고 여부 수정, 콘텐츠(카테고리 수정), 타켓 수정은 \[앱 콘텐츠]페이지에서 수정가능합니다.

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B85new.png)

**정책 → 앱 콘텐츠 페이지로 이동하면 각 섹션별 내용 수정이 가능합니다.**&#x20;

예를들어 앱 출시 후에 광고가 들어간 버전으로 업데이트 되었다면, **광고포함에 반드시 체크를 해주셔야 해요.**

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%BA%A1%EC%B2%98.1PNG.png)

앱 정보 – 앱 콘텐츠 메뉴를 선택하면 → 광고 섹션이 있습니다.

관리 버튼을 눌러서  **“예, 광고가 포함되어 있습니다.” 에 체크한 뒤 저장 버튼을 눌러주시면 됩니다.**&#x20;

<mark style="color:red;">**\*앱 콘텐츠 수정도 업데이트 심사 후 반영이 됩니다.**</mark>&#x20;

<figure><img src="../../.gitbook/assets/구분선 (1) (2).PNG" alt=""><figcaption></figcaption></figure>

## ![](https://wp.swing2app.co.kr/wp-content/uploads/2020/04/%EB%8B%A8%EB%9D%BD1-e1611212616323.png) STEP5. 플레이스토어 앱업데이트 안내사항



**1.플레이스토어에 출시된 앱은 자유롭게 업데이트가 가능합니다. (제한이 있지 않아요!)**

따라서 앱 버전 업데이트, 스토어 등록정보를 수정하고 싶을 때 위에 알려드린 방법으로 진행해주세요.



**2.안드로이드폰에서는 플레이스토어에서 다운 받은 앱이 업데이트 되어도, 앱 실행시 업데이트 안내 창이 뜨지 않을 수 있습니다.**



**3. 플레이스토어에 앱 업데이트가 완료되어도, 안드로이드폰마다 업데이트 되는 시간이 다릅니다.**

플레이스토어에서 업데이트 완료되었다고 떠도, 실제 안드로이드폰으로 배포 되는 시간이 다 다릅니다. (반영시간 24시간\~48시간 이내)

따라서 구글 플레이 콘솔에서 업데이트 되었다고 해도, 앱은 아직 업데이트가 되지 않는 경우가 있습니다.

배포 시간이 다르기 때문에 시간을 가지고 기다려 주시기 바랍니다.



**4.자동업데이트 설정 되어 있기 때문에, 앱 업데이트건이 있을 경우 사용자의 핸드폰 데이터 환경에서 자동으로 업데이트 됩니다.**

안드로이드폰마다 설정된 구글플레이 업데이트 설정에 따라 사용자 기기에서 자동으로 업데이트 됩니다.

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8-1.png)

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%ED%94%8C%EB%A0%88%EC%9D%B4%EC%96%B4%ED%94%8C4-1.png)

이미지처럼, 보통 안드로이드폰은 업데이트가 자동으로 설정되어 있습니다.

따라서 업데이트가 되어도 별도 안내 창이나 팝업 없이, 사용자의 안드로이드폰 환경에 따라 자동 업데이트 됩니다.

<mark style="color:red;">\*그러나 사용자가 업데이트 하지 않음으로 설정해도, 앱 개발사(개발자)가 어떠한 조치를 취할 수 없습니다.</mark>

업데이트를 해도 사용자마다 업데이트를 하고, 안하는 것은 사용자 선택이며 따라서 폰에서의 앱 업데이트 반영 시간도 모두 다릅니다.

플레이스토에 앱을 업데이트 하셨다면, 해당 내용을 반드시 유념해주세요!



**5. 업데이트도 앱심사와 동일하게 심사시간이 있습니다.  최소 1일\~ 최대 7일까지 소요**

업데이트 심사일 소요시간 편차가 크기 때문에 업데이트 심사 제출 후 업데이트 완료될 때가지기다려주시기 바랍니다.

심사 완료 후에 플레이스토어에 업데이트 한 내용이 반영됩니다.



**6. 플레이스토어는 소프트 업데이트(앱 내 자동 업데이트)를 금지하고 있습니다. **<mark style="color:red;">**\*중요\***</mark>

앱 업데이트는 하드 업데이트로 진행한 뒤, 앱 버전을 플레이스토어에도 동일하게 등록해주셔야 합니다.

업데이트 버전이 다를 경우 출시 후에도 앱이 삭제될 수 있습니다.

\*플레이스토어 앱 이용중인 사용자분들은 업데이트 진행시- 업데이트 유형을 ‘하드 업데이트’로 설정해주세요.

\*앱스토어에 앱 출시가 안된 분들은 ‘업데이트 표시 안함’으로 체크 후 제작하셔도 됩니다.



**7. 구글 필터링 주의!!**

처음에 정상적으로 출시가 되었던 앱이, 업데이트 후에 갑자기 정책위반을 이유로 앱이 삭제되는 경우가 종종 있습니다.

따라서 앱 업데이트를 하실 때에도 구글 정책에 위반되는 내용이 없는지 꼭 확인해주시기 바랍니다.!!

