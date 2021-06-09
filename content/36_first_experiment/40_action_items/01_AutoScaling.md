+++
title = "2.5.1 Auto Scaling"
chapter = true
weight = 01
+++

# 2.5.1 Auto Scaling
## 수정 : Auto Scaling 설정

[AWS 콘솔](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#Home:)으로 이동하고 서비스에서 EC2를 선택합니다.

![AWS Auto Scaling groups](/images/aws_auto_scaling.png)

왼쪽 탐색 모음에서 **Auto Scaling Groups**을 선택합니다.

![AWS Auto Scaling groups](/images/aws_automatic_scaling.png) 

각 클러스터에는 자체 Auto Scaling 그룹이 있습니다. 계속해서 필요한 것을 확인하십시오. 다음 섹션에서 **Automatic scaling**을 선택한 다음 **Add Policy**를 선택합니다.

For **"Policy type"** select **"Simple scaling"**

For Scaling Policy name, feel free to call it **`ScaleUp`**.

![AWS Auto Scaling groups](/images/aws_create_scaling_policy_prework.png) 

We are going to need to setup a CloudWatch Alarm, go ahead and select **"Create a CloudWatch alarm"**.

**"Policy type"**에서 **"Simple scaling"**을 선택합니다.

Scaling Policy 이름은 **`ScaleUp`**이라고 부릅니다.

![AWS Auto Scaling Groups](/images/aws_create_scaling_policy_prework.png)

CloudWatch 경보를 설정하고 **"Create a CloudWatch alarm"**를 선택합니다.
