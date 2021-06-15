---
title: "Cloud9"
chapter: false
weight: 10
---

[AWS Cloud9](https://aws.amazon.com/cloud9/)는 브라우저만으로 코드를 작성, 실행, 디버깅 할 수 있는 클라우드 기반 통합 개발 환경(IDE)입니다. 여기에는 코드 편집기, 디버거 및 터미널이 포함됩니다. Cloud9에는 자바 스크립트, Python, PHP 등 인기있는 프로그래밍 언어를 위한 필수 도구가 사전 패키징되어 있으므로 새 프로젝트를 시작하기 위해 파일을 설치하거나 개발 시스템을 구성 할 필요가 없습니다.

### 새 Cloud9 IDE 환경 추가

1 . AWS 콘솔 내에서 리전 목록을 사용하여 **us-west-2(오레곤)**를 선택합니다. 워크샵 스크립트가 동일한 지역의 리소스를 제공하기 때문에 이 작업을 수행합니다.

![image](/images/aws-pick-region.png)

2. [cloud9 콘솔](https://console.aws.amazon.com/cloud9/home)로 이동하거나 **AWS 콘솔 서비스** 메뉴에서 검색하면 됩니다.

![image](/images/c9-search.png)

3 . `Create environment` 버튼을 클릭합니다.

![image](/images/c9-create.png)

4 . `gremlin-workshop` 이름을 입력합니다.


5 . 기타 인스턴스 유형을 선택하고 t3.medium을 선택합니다.


6 . 다른 모든 설정은 기본값으로 둡니다.

![image](/images/c9-settings.png)

{{% notice info %}}
프로비저닝하는 데 약 1 ~ 2 분 정도 걸립니다.
{{% /notice %}}

### Cloud9 IDE 환경 구성

환경이 나타나면 다음과 같이 환경을 사용자 정의하십시오.

1 . **welcome page** 탭을 닫습니다.

2 . **lower work area** 탭을 닫습니다.

3 . 기본 작업 환경에서 새 **terminal** 탭을 엽니다.


![c9before](/images/c9before.png)

이제 작업 환경이 다음과 같아야하며 왼쪽 **environment** 탭을 클릭하여 왼쪽 환경 탐색기를 숨길 수 있습니다.

![c9after](/images/c9after.png)

{{% notice tip %}}
이 어두운 테마가 마음에 들지 않으면 **View / Themes** Cloud9 작업 환경 메뉴에서 변경할 수 있습니다.
{{% /notice %}}

{{% notice tip %}}
Cloud9에는 타사 쿠키(third-party-cookies)가 필요합니다. [특정 도메인](https://docs.aws.amazon.com/cloud9/latest/user-guide/troubleshooting.html#troubleshooting-env-loading)을 화이트리스트에 추가 할 수 있습니다. 이에 문제가 있습니다. 광고 차단기, 자바 스크립트 비활성화기 및 추적 차단기는 cloud9 도메인에 대해 비활성화 해야합니다. 그렇지 않으면 작업 환경에 대한 연결이 영향을 받을 수 있습니다.
{{% /notice %}}