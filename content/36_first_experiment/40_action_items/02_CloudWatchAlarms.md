+++
title = "2.5.2 CloudWatch 경보"
chapter = true
weight = 02
+++

# 2.5.2 CloudWatch 경보
## Auto Scaling 설정 : Cloudwatch 구성

먼저 경보할 측정 항목을 찾아야 합니다. **"Select Metric"**, **"ContainerInsights"**, **"ClusterName, InstanceId, NodeName"**을 차례로 선택합니다. EC2 인스턴스에서 `node_cpu_utilization`을 찾아 **"Select Metric"**을 누릅니다.

![Container Insights Results](/images/aws_select_cpu_utilization.png)

 이제 메트릭과 조건을 지정합니다. 첫 번째 섹션에서 기간을 **"1 minute"**으로 변경합니다.

![Container Insights Results](/images/aws_period_1min.png)

**"Conditions"**으로 이동하겠습니다.

1. **Static**은 선택된 상태로 둡니다.
2. **"Greater"**를 선택합니다.
3. 임계값 상자에 **`50`**을 입력합니다.
계속해서 **"Next"**을 누릅니다.


![Threshold 50](/images/aws_conditions_50.png)


> **CPU가 50보다 크면 알람이 트리거됩니다.**

이제 알람이 트리거 될 때 발생하는 작업을 구성해야 합니다.
페이지 상단의 **Notification**" 하단의 **Add notification** 버튼을 누릅ㅂ니다.

**"Alarm state trigger"**의 경우 **"In alarm"**으로 둡니다. 그 아래에서 **"Create new Topic"**을 선택합니다. 주제에 이름을 지정하고 `CPU_Increase`를 사용하겠습니다. 이제 알림을 받을 이메일을 주고 **Create topic**를 누릅니다.

마지막으로 나머지는 모두 그대로 두고 **"Next"**을 누릅니다.

![Configure Alarm](/images/aws_configure_alarm_actions.png)

`AWS Notification - Subscription Confirmation`이라는 제목의 이메일을 받으면 해당 이메일로 이동하여 **"Confirm subscription"** 링크를 클릭합니다.

![AWS Notification - Subscription Confirmation](/images/aws_notification_subscription_confirmation.png)

그러면 다음과 같은 확인이 표시됩니다.
![AWS Notification - confirmed](/images/aws_subscription_confirmed.png)


CloudWatch "Configure actions" 페이지로 돌아가 이제 경보 이름을 지정하고 간단하게 유지하고 `ScaleUp-Alarm` 이름을 지정하고 **"Next"**를 누릅니다. 계속해서 단계를 검토하고 **"Create alarm"**를 누르는 것을 잊지 마세요.