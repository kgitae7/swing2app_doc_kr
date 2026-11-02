---
hidden: true
---

# 앱스토어 빌드 등록

새 빌드 업로드 방법

빌드 파일 등록은 크게 두 가지 방법이 있습니다.

**방법 A. Xcode로 업로드**

iOS 소스코드가 있고 직접 빌드해야 할 때 사용하는 방법입니다.

**방법 B. Transporter로 업로드**

개발사에서 이미 완성한 IPA 파일을 전달받았을 때 간편하게 등록하는 방법입니다.

&#x20;

방법 A. Xcode를 이용한 빌드 등록

1. Mac에서 Xcode 실행
2. 기존 앱의 프로젝트 파일(.xcodeproj 또는 .xcworkspace) 열기
3. Target → General에서 Version, Build 번호 설정
4. Signing & Capabilities에서 개발자 팀과 서명 설정 확인
5. 상단 메뉴 Product → Archive 선택
6. Archive 생성 후 Organizer에서 Distribute App 선택
7. TestFlight & App Store 선택
8. 검증 및 서명 절차를 확인하고 업로드 진행

최신 Xcode는 자동 서명 및 업로드 과정을 지원합니다.

[https://developer.apple.com/documentation/Xcode/distributing-your-app-for-beta-testing-and-releases?changes=l\_6\&utm\_source=chatgpt.com](https://developer.apple.com/documentation/Xcode/distributing-your-app-for-beta-testing-and-releases?changes=l_6\&utm_source=chatgpt.com)

&#x20;

방법 B. IPA 파일을 Transporter로 등록

이미 IPA 파일을 보유하고 있다면 이 방법이 더 간단합니다.

1. Mac App Store에서 [Transporter 설치](https://apps.apple.com/app/transporter/id1450874784?utm_source=chatgpt.com)
2. Transporter 실행
3. 해당 앱에 접근 권한이 있는 Apple 계정으로 로그인
4. .ipa 파일을 프로그램에 추가
5. 전송(Deliver) 버튼 클릭
6. 업로드 완료 여부 확인

이 과정에서는 Xcode 소스코드가 없어도 됩니다. 다만 IPA가 앱스토어 배포용으로 정상 빌드·서명되어 있어야 합니다.

[https://support.apple.com/ko-kr/guide/transporter-app/welcome/mac?utm\_source=chatgpt.com](https://support.apple.com/ko-kr/guide/transporter-app/welcome/mac?utm_source=chatgpt.com)

&#x20;

&#x20;**4. 업로드한 새 빌드를 앱 버전에 연결**

업로드가 완료되면 App Store Connect에서 다음과 같이 진행합니다.

1. 업데이트할 앱 선택
2. 왼쪽에서 신규 생성한 iOS 버전 선택
3. 화면을 아래로 내려 빌드(Build) 항목 찾기
4. \+ 버튼 클릭
5. 업로드한 새로운 빌드 선택
6. 완료 → 저장

빌드가 보이지 않는다면 Apple의 빌드 처리 과정이 끝났는지 TestFlight 탭에서 확인하세요.

[https://developer.apple.com/help/app-store-connect/manage-builds/choose-a-build-to-submit?utm\_source=chatgpt.com](https://developer.apple.com/help/app-store-connect/manage-builds/choose-a-build-to-submit?utm_source=chatgpt.com)



### 5. 앱심사 제출

빌드 선택까지 완료했다면 다음과 같이 진행합니다.

1. 새로운 기능 및 변경사항 입력
2. 필수 앱 정보 및 규정 준수 항목 확인
3. 심사에 추가(Add for Review) 선택
4. 심사를 위해 제출(Submit for Review) 클릭

심사에 제출하기 전까지는 등록할 빌드를 변경할 수 있습니다.

{% embed url="https://developer.apple.com/kr/help/app-store-connect/manage-submissions-to-app-review/submit-an-app?utm_source=chatgpt.com" %}





이미 출시된 앱을 1.0.1로 업데이트하는 경우

기존 `1.0.0` 앱이 이미 '배포 준비됨' 상태라면 다음과 같이 새 버전을 생성할 수 있습니다.

1. 기존 앱 선택 → 왼쪽 `iOS 앱` 옆 + 클릭
2. 새 버전 번호 `1.0.1` 입력 → 생성
3. 새 버전의 앱 정보와 '이번 버전의 새로운 기능' 입력
4. '빌드' 항목의 + 클릭
5. 이미 업로드된 `1.0.1` 빌드 선택
6. 완료 → 저장
7. 심사에 추가 → 심사를 위해 제출

앱이 심사를 통과한 이후 자동 출시되지 않게 하려면, 버전 화면의 App Store 버전 출시 → 앱을 직접 출시를 선택하시면 됩니다&#x20;

{% embed url="https://developer.apple.com/kr/help/app-store-connect/manage-your-apps-availability/select-an-app-store-version-release-option?utm_source=chatgpt.com\" %}



### 4. 새 빌드가 목록에 보이지 않는 경우

| 증상            | 확인할 사항                                |
| ------------- | ------------------------------------- |
| + 버튼이 나타나지 않음 | 기존 빌드가 연결되어 있거나 버전 상태가 잠겨 있는지 확인      |
| 새 빌드가 목록에 없음  | 새 빌드의 앱 버전이 현재 App Store 버전과 일치하는지 확인 |
| 빌드가 처리 중      | TestFlight에서 빌드 처리 완료 여부 확인           |
| 심사에 추가할 수 없음  | 이전 제출의 해결되지 않은 문제 및 제출 초안 상태 확인       |







### 3. Transporter에서 IPA 업로드

[Transporter | macOS Icon Gallery](https://images.openai.com/static-rsc-4/AWs2wchjsxM48Y1DapMfOxl91aBZ6nlC8rOB-I3MF_R_1M8pPBHhxeSz6n0Nxc2QfSIVi6TsNWa4U_DNhptAeIJOwzW1PiO26p060NOXMw7K1-yczsg4b6A80F7vn2-8GuzpdazSpYKrQ_B4H0zYWBA99VPKuqvCWOBNeouNMW0?purpose=inline)

Apple Transporter

Apple에서 제공하는 공식 앱 바이너리 업로드 프로그램입니다.

[Mac App Store에서 Transporter 설치](https://apps.apple.com/app/transporter/id1450874784?utm_source=chatgpt.com)

**① Transporter 실행 및 로그인**

1. Mac에서 Transporter를 실행합니다.
2. Sign In(로그인) 버튼을 클릭합니다.
3. 고객사 앱에 접근 권한이 있는 Apple 계정으로 로그인합니다.
4. 이중 인증이 나오면 인증을 완료합니다.
5. 계정이 여러 조직에 속해 있다면 대상 고객사의 Provider(제공업체)가 맞는지 확인합니다.

#### ② IPA 파일 등록

1. Transporter 화면에서 \*\*+ 버튼 또는 Add App(앱 추가)\*\*을 클릭합니다.
2. &#x20;`.ipa` 파일을 선택합니다.
3. 또는 IPA 파일을 Transporter 화면으로 끌어다 놓습니다.
4. 업로드할 파일이 목록에 추가되었는지 확인합니다.

#### ③ Apple 서버에 업로드

1. 등록된 IPA 파일 옆의 Deliver(전송) 버튼을 클릭합니다.
2. Transporter가 파일 검증과 업로드를 진행합니다.
3. 완료 후 Delivered(전송 완료) 상태를 확인합니다.
4. 오류가 발생하면 전송 로그에서 원인을 확인합니다.

