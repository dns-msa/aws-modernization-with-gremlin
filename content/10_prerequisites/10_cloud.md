---
title: "작업 공간에 대한 IAM 설정 업데이트"
chapter: false
weight: 19
---

{{% notice info %}}
Cloud9는 일반적으로 IAM 자격 증명을 동적으로 관리합니다. 현재 EKS IAM 인증과 호환되지 않으므로 이를 비활성화하고 대신 IAM 역할에 의존합니다.
{{% /notice %}}

- 작업 공간으로 돌아가서 톱니 바퀴 아이콘(오른쪽 상단 모서리에 있음)을 클릭하거나 클릭하여 새 탭을 열고 "Open Preferences"를 선택합니다.
- **AWS SETTINGS**를 선택합니다.
- **AWS managed temporary credentials** 끄기
- 환경 설정 탭 닫기
![c9disableiam](/images/c9disableiam.png)

임시 자격 증명이 아직 없는지 확인하기 위해 기존 자격 증명 파일도 제거합니다.
```sh
rm -vf ${HOME}/.aws/credentials
```
jq 설치합니다 - jq는 JSON 구문 분석을 위한 명령줄 도구입니다.
```sh
sudo yum install jq
```
현재 리전을 기본값으로 사용하여 aws cli를 구성해야 합니다.

{{% notice info %}}
[AWS 이벤트에 참석](https://eksworkshop.com/020_prerequisites/aws_event/)중인 경우 강사에게 **AWS 리전**을 사용할 것인지 문의하십시오.
{{% /notice %}}

```sh
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
```

AWS_REGION이 원하는 지역으로 설정되어 있는지 확인합니다.
```sh
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set
```
 
이것들을 bash_profile에 저장합니다.
```sh
echo "export ACCOUNT_ID=${ACCOUNT_ID}" | tee -a ~/.bash_profile
echo "export AWS_REGION=${AWS_REGION}" | tee -a ~/.bash_profile
aws configure set default.region ${AWS_REGION}
aws configure get default.region
```

### IAM 역할 검증

[GetCallerIdentity](https://docs.aws.amazon.com/cli/latest/reference/sts/get-caller-identity.html) CLI 명령을 사용하여 Cloud9 IDE가 올바른 IAM 역할을 사용하고 있는지 확인합니다.

```
aws sts get-caller-identity --query Arn | grep Pulumi-Workshop-Admin -q && echo "IAM role valid" || echo "IAM role NOT valid"
```

<!--
First, get the IAM role name from the AWS CLI.
```bash
INSTANCE_PROFILE_NAME=`basename $(aws ec2 describe-instances --filters Name=tag:Name,Values=aws-cloud9-${C9_PROJECT}-${C9_PID} | jq -r '.Reservations[0].Instances[0].IamInstanceProfile.Arn' | awk -F "/" "{print $2}")`
aws iam get-instance-profile --instance-profile-name $INSTANCE_PROFILE_NAME --query "InstanceProfile.Roles[0].RoleName" --output text
```
-->

IAM 역할이 유효하지 않은 경우 <span style = "color: red;">**계속하지 마십시오**</span>. 돌아가서 이 페이지의 단계를 확인하십시오.

이 섹션의 끝에 도달한 경우 [**Workshop 설정**](/15_workshop_setup/50_workshop_setup.html) 섹션으로 건너 뛸 수 있습니다.
