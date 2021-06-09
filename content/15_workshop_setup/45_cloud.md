---
title: "작업 공간에 대한 IAM 설정 업데이트"
chapter: false
weight: 19
---

{{% notice info %}}
Cloud9는 일반적으로 IAM 자격 증명을 동적으로 관리합니다. 
현재 EKS IAM 인증과 호환되지 않으므로 이를 비활성화하고 대신 IAM 역할에 의존합니다.
{{% /notice %}}

- 작업 공간으로 돌아가서 톱니 바퀴 아이콘(오른쪽 상단 모서리에 있음)을 클릭하거나 클릭하여 새 탭을 열고 "Open Preferences"를 선택합니다.
- **AWS SETTINGS**를 선택합니다.
- **AWS managed temporary credentials** 끄기
- 환경 설정 탭 닫기

![c9disableiam](/images/c9disableiam.png)


아래 명령을 실행해 보겠습니다. 그러면 다음과 같은 작업이 수행됩니다.

:small_blue_diamond: jq 설치 - jq는 JSON 구문 분석을 위한 명령줄 도구입니다.

:small_blue_diamond: 임시 자격 증명이 아직 준비되지 않았는지 확인합니다.

:small_blue_diamond: 기존 자격 증명 파일을 제거합니다.

:small_blue_diamond: 원하는 지역에서 작동하도록 지역을 설정합니다.

:small_blue_diamond: IAM 역할이 유효한지 확인합니다.

```sh
sudo yum -y install jq
rm -vf ${HOME}/.aws/credentials
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set
echo "export ACCOUNT_ID=${ACCOUNT_ID}" | tee -a ~/.bash_profile
echo "export AWS_REGION=${AWS_REGION}" | 
tee -a ~/.bash_profile
aws configure set default.region ${AWS_REGION}
aws configure get default.region
aws sts get-caller-identity --query Arn | grep Gremlin-Workshop-Admin -q && echo "IAM role valid" || echo "IAM role NOT valid"
```

IAM 역할이 유효하지 않은 경우 <span style="color: red;"> **계속하지 마십시오** </span>. 돌아가서 이 페이지의 단계를 확인하십시오.