---
title: "작업 환경에 IAM 역할 연결"
chapter: false
weight: 17
---

1. [Cloud9 EC2 인스턴스를 찾으려면 이 링크](https://console.aws.amazon.com/ec2/v2/home?#Instances:tag:Name=aws-cloud9-.*workshop.*;sort=desc:launchTime)를 참고하세요.
1. 인스턴스를 선택한 다음 **Actions / Instance Settings / Attach / Replace IAM Role**을 선택합니다.
![c9instancerole](/images/c9instancerole.png)
1. **IAM Role** 드롭 다운에서 **Pulumi-Workshop-Admin**을 선택하고 **Apply**을 선택합니다.
![c9attachrole](/images/c9attachrole.png)