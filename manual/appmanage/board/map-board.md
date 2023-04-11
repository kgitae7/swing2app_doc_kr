---
description: 위치등록 - 지도 게시판 등록 및 이용방법
---

# 위치등록(지도)게시판

<figure><img src="../../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

**위치등록 게시판이란?**

어플 제작 시에 업체 주소를 넣어야 할 때\~!! **고객들에게 지도 및 오시는 길 안내를 해야 할 때 사용할 수 있는 위치등록 기능이구요**.

지도 기능은 카카오맵과 연동하여 제공하고 있습니다.

지도 게시판은 지도map 제공 뿐만 아니라 **업체의 주소, 업체 설명, 길 찾기, 홈페이지, 전화걸기, 사진(이미지)** 등 다양한 상세 정보를 입력할 수 있습니다.



\*구글맵 게시판도 있으니, 해외 주소를 사용해야 할 경우 구글맵을 이용해주세요 \~!

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/board/google-map" %}

<figure><img src="../../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

<mark style="color:blue;">**앱 실행화면 – 지도게시판**</mark>&#x20;

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90\_8.13.png)

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%85%B9%ED%99%94\_2019\_07\_24\_16\_18\_40\_943.gif)

앱 실행화면을 통해서 지도게시판이 어떻게 보여지는지 확인해주시구요.

아래에서 지도게시판을 만들고 앱에 적용하는 과정을 모두 알려드리겠습니다\~!

<figure><img src="../../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## STEP1. 지도 게시판 생성

* **먼저 게시판관리 메뉴에서 지도 게시판을 추가해야 하겠죠?**

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90NEW3.png)

[앱운영 페이지 → 서비스관리 ](http://www.swing2app.co.kr/view/board\_edit)→ 게시판 관리 로 이동합니다.



![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90NEW2.png)

게시판 관리 페이지에서 <mark style="color:blue;">**\[게시판 생성]**</mark> ​버튼을 선택하면 게시판 설정 창이 뜹니다.



### <mark style="color:blue;">**1.기본설정**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%9C%84%EC%B9%98%EB%93%B1%EB%A1%9D\_19.png)

1\)게시판 및 기능 이름 : 게시판 이름을 작성합니다.

2\)서비스 용도: 사용자 정의를 선택해주세요.

3\) UI 및 기능 선택 : \[위치등록]을 선택해주세요.

4\) 지도보기 권한 선택: 지도게시판 누구에게 보여줄지 권한을 선택해주세요.

모든 앱이용자에게 보여줄 경우 ‘손님’으로 설정하고, 그외 다른 사용자 권한이 있을 경우 선택해주세요.

5\) 지정 권한 사용기능 허용: 특정 등급의 사용자만 이용하게 하는 옵션 기능인데요.옵션을 사용하지 않을 경우 ‘사용안함’으로 체크합니다.

\*게시판 지정권한에 대한 상세 내용은 아래 매뉴얼 링크를 선택해주세요.

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/board/designated-authority" %}

6\)  \[저장하기]버튼을 눌러주세요.

<mark style="color:red;">​\*다음 항목인 ‘고급설정’을 입력하실 경우 고급설정까지 모두 입력 후 저장 버튼을 선택하고, 고급설정을 입력하지 않을 경우 바로 저정해주세요.</mark>

{% hint style="info" %}
**지도게시판은 기능설명 문구는 입력하지 않습니다.**

\+지도를 볼 수 있는 권한을 설정해야 할 경우(옵션 추가) **서비스용도에서 ‘사용자 정의’를 선택하면 고정된 회색 영역이 풀려요.**

\+UI 및 기능선택에 ‘위치등록’을 선택한 뒤 권한 설정, 지정권한 허용 등의 옵션을 이용해주시면 되겠습니다.

\+위치등록 밑에 보이는 **위치등록(구글맵)은 구글지도를 연동하는 지도게시판이에요.**

해외 주소를 사용하여 지도게시판을 만들어야 할 경우 위치등록(구글맵)을 이용해주세요\~
{% endhint %}



### <mark style="color:blue;">**2.고급설정**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2020/11/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90-%EA%B3%A0%EA%B8%89%EC%84%A4%EC%A0%958.png)

2번째 메뉴인 고급설정을 선택하면 추가 항목을 설정할 수 있습니다.

고급설정은 필수 입력항목은 아니기 때문에 기본설정만 입력하고 저장하셔도 되고, 고급설정에서 몇가지 항목을 수정할 수 있습니다.

고급설정 이용방법은 아래 매뉴얼을 참고해주세요!

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/board/map-advancedsettings" %}

만든 게시판에 위치를 등록해보겠습니다.

<figure><img src="../../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## STEP2. 지도게시판 – 위치등록하기

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90.png)

앱운영 페이지 → 게시물관리 → 만들어놓은 ‘지도게시판’으로 이동합니다.\


![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90%EC%88%98%EC%A0%952.png)

지도 게시판 화면에 보시면 **검색창이 있구요.**

**주소를 입력하거나, 다음(카카오맵)에 등록된 업체라면 업체나 회사명, 키워드를 검색해서도 추가할 수 있습니다.**



![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/e035eb92f5c6be6bade780e7e0a2ae46.png)

주소및 키워드 입력이 완료되면 위치 등록이 완료되구요.

이렇게 위치가 하나 추가 된 것을 확인할 수 있어요.

**\[추가]** 버튼을 선택해서 위치에 대한 정보 및 상세정보 등을 입력해주세요.\


![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/e118ee3918dbe9845db11c6a138072e4.png)

**\[추가] 버튼 선택시 위치등록 창이 뜨며, 상세 설명을 입력할 수 있습니다.**

1\)상호: 상호명을 입력합니다. \*실제 회사명을 입력해도 좋고, 사용자들에게 소개할 문구를 작성해주세요.

2\)주소: 앞서 검색한 주소 외에 상세 주소를 모두 입력합니다.

3\)설명: 업체를 설명하는 소개글을 써주세요.

4\)전화번호: 전화번호를 입력합니다.

5\)홈페이지: 홈페이지나 운영하는 블로그, 카페 URL링크를 입력합니다.

6\)이미지등록: 이미지 등록이 가능합니다. 업체 내부 사진 및 업체 홍보용 사진이 있다면 등록해주세요.

7\)모든 내용 입력이 완료되면 저장하기 버튼을 선택합니다.\
\
<mark style="color:red;">★ 홈페이지, 전화번호, 사진이 없는 경우 입력하지 않아도 괜찮아요.</mark>&#x20;

<mark style="color:red;">입력된 항목들만 게시판에서 표시가 됩니다.</mark>&#x20;

<mark style="color:red;">★ 우선순위는 지도(위치)를 여러개 등록하는 경우, 앱에서 보여지는 순서를 정할 수 있습니다.</mark>&#x20;

<mark style="color:red;">(위치 하나만 등록하는 경우 우선순위 입력하지 않아도 됩니다)</mark>\
\


![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/ad89fae4f045f3dc79c3bbf78cd9efd1.png)

**위치 등록이 완료되었습니다.**&#x20;

지도 게시판은 이렇게 주소 및 키워드로 위치를 추가할 수 있구요.\


![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%9C%84%EC%B9%98%EB%93%B1%EB%A1%9D4\_19.10.png)

**등록된 주소지를 선택하면 위치 수정 및 삭제가 가능합니다.**

그리고 여러 업체들을 관리하는 앱이라면 여러 업체들의 주소를 추가하여 등록 할 수 있어요\~



<mark style="color:orange;">**위치를 추가할 때는 어떻게 하나요?**</mark>

**위치를 하나 더 등록하고 싶을 때는 동일하게 \[검색창열기]를 선택해서 위치를 추가를 할 수 있습니다.**\


![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/8b9f53b2dba31c12e8c77e4532f1f31c.png)

![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/7ab1211ccedc9cf52ee95523b784e0db.png)

![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/a61acd948999981eac859916a30c95b8.png)

예시로 맥도날드 강남점 키워드 검색을 하여 각 지점들을 추가해보았어요.

지도게시판은 여러 위치를 이용할 경우 이렇게 주소 및 키워드로 검색한 뒤 추가하여 사용하시면 됩니다.

그럼, 지도 게시판에 위치를 등록했으니 앱에 해당 게시판을 적용해야 하겠죠?

앱제작 페이지로 이동하여서 앱에 게시판을 적용해볼게요

<figure><img src="../../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## &#x20;STEP3. 앱에 지도게시판 적용하기



<mark style="color:blue;">**앱제작 V3버전 이용시)**</mark>

<figure><img src="../../../.gitbook/assets/위치등록.png" alt=""><figcaption></figcaption></figure>

1\)앱제작–STEP3 페이지 선택

2\)메뉴 선택

\*메뉴를 만들기 전이라면, 새 메뉴를 만들어주세요. (+ 모양 버튼 선택하여 메뉴 추가)

3\) 메뉴 이름을 입력해주세요.

4\) 페이지 디자인에서 \[UI KIT] 선택

5\)\[위치등록]을 선택해주세요.&#x20;

6\) 만들어놓은 위치등록 게시판을 확인한 뒤 \[적용하기] 버튼을 선택해주세요. (페이지에 마우스 커서를 가져다 대면 적용하기 버튼이 열립니다)

<mark style="color:red;">\*위치등록게시판을 먼저 만들어주세요. 만들어놓은 위치등록 게시판이 없을 경우 화면에 뜨지 않으며, 앱에 적용할 수 없습니다.</mark>&#x20;

<mark style="color:red;">\*UI KIT 화면에 있는 \[새로 만들기] 버튼을 선택하거나, 앱운영-서비스관리- 게시판관리에서도 게시판을 만들 수 있습니다.</mark>

7\) 화면 상단 \[저장]버튼을 누르면 앱에 적용됩니다.

\*제작 단계 중 메뉴 아이콘 , 메뉴 설정은 필수 입력 항목이 아닙니다.

해당 매뉴얼에서는 입력 없이 진행했으며, 앱 제작시 필요할 경우 추가로 적용해주세요.



<mark style="color:blue;">**앱제작 V2버전 이용시)**</mark>

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90NEW1.png)

**앱제작 페이지 → 페이지 메뉴로 이동해주세요.**

1\) 지도게시판을 어디로 적용시킬지 확인하여 \[카테고리 추가] 버튼을 선택하여 메뉴를 추가합니다.&#x20;

2\) 메뉴 이름을 입력해주세요.

3\) 메뉴 유형: \[게시판]을 선택해주세요.

4\) \[링크마법사] 버튼을 선택해주세요.

5\) 메뉴에 적용할 ‘위치등록 지도’ 게시판을 선택한 뒤 \[반영] 버튼 선택

6\) \[적용] 버튼

7\) \[저장] 버튼을 누르면 완료됩니다.

\*아이콘은 선택사항이며, 메뉴 앞에 아이콘을 적용할 경우만 선택해주세요.&#x20;



<figure><img src="../../../.gitbook/assets/구분선 (1).PNG" alt=""><figcaption></figcaption></figure>

## STEP4. 앱 실행화면

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EC%A7%80%EB%8F%84%EA%B2%8C%EC%8B%9C%ED%8C%90-%EB%94%94%EC%9E%90%EC%9D%B8%EB%B3%80%EA%B2%BD.png)

지도게시판은 **\[리스트 열기]**를 선택하여 적용된 위치등록 목록을 확인할 수 있어요.

여러 위치를 등록했다면,리스트에서 등록한 위치 목록을 확인할 수 있습니다.

![](https://wp.swing2app.co.kr/wp-content/uploads/2018/09/%EB%85%B9%ED%99%94\_2019\_07\_24\_16\_18\_40\_943.gif)

**\[전화걸기] 버튼을 선택하면 입력된 전화번호로 바로 전화연결이 됩니다.**

**\[길안내] 버튼을 선택하면 카카오 지도 사이트로 이동하여 길찾기가 가능합니다.**

**\[홈페이지] 버튼을 선택하면 적용된 홈페이지 URL로 페이지가 이동합니다.**

**\[사진보기]를 선택하면 등록한 이미지를 볼 수 있어요.**

**여러 이미지를 등록했을때에도 이미지를 손으로 슬라이딩하여 넘겨서 볼 수 있습니다.**

***

스윙투앱에서 제공하는 지도게시판은!

주소, 지도, 길안내 뿐만 아니라 업체의 홈페이지, 전화번호, 이미지 등록까지 할 수있기 때문에 업체홍보 활용도가 높습니다.&#x20;

어플 제작시에 위치등록 서비스를 추가해서 제작해보세요 ^^

쉬운 방법으로 앱에서 업체 홍보를 효과적으로 진행할  수 있습니다. \~!!



해외 위치 등록을 해야한다면 구글맵 게시판을 이용해주세요 \~

{% embed url="https://documentation.swing2app.co.kr/manual/appmanage/board/google-map" %}



