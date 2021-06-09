+++
title = "2.5.4 AutoScaling Down 설정"
chapter = true
weight = 04
+++

# 2.5.4 AutoScaling Down 설정


## Auto Scaling Down을 설정합니다.

이전과 동일한 단계를 따르고 싶지만 대신 **`ScaleDown`** 이라는 새 정책을 추가하고 이에 대한 새 경보를 생성합니다.

> 이 경보는 CPU 사용률이 1분 내에 30% 이하 (<=) 일 때 발생합니다.

**"ScaleUp"** 정책을 볼 수 있으며 이제 **"Add Policy"**를 눌러 자동 축소 정책을 설정합니다.
![Container Insights Results](/images/aws_create_down_policy.png)

다음 페이지에서 **Automatic scaling**을 선택한 다음 **Add Policy**를 선택합니다.

**"Policy type"**에서 **"Simple scaling"**을 선택합니다.

Scaling Policy 이름은 **`ScaleDown`**이라고 입력합니다. 이제 새 CloudWatch 경보를 설정하고 **"Create a CloudWatch alarm"**을 선택해야 합니다.

## Auto Scaling 설정 : Cloudwatch 구성

먼저 경보 할 측정 항목을 찾아야합니다. **"Select Metric"**, **"Container Insights"**, **"ClusterName, InstanceId, NodeName"**을 차례로 선택합니다. `node_cpu_utilization`을 찾아 **"Select Metric"** 을 누릅니다.


![Container Insights Results](/images/aws_select_cpu_utilization.png)

이제 메트릭과 조건을 지정합니다. 첫 번째 섹션에서 기간을 **"1 minute"**으로 변경합니다.

![Container Insights Results](/images/aws_period_1min.png)

**"Conditions"**으로 이동하겠습니다.

1. **Static**은 선택된 상태로 둡니다.
2. **"Lower/Equal"**을 선택합니다.
3. 임계값 상자에 **`30`**을 입력합니다.
계속해서 **"Next"**을 누릅니다.


> ** CPU가 30 % 이하이면 알람이 트리거됩니다. **

![Threshold 30](/images/aws_conditions_30.png)


이제 알람이 트리거 될 때 발생하는 작업을 구성해야 합니다.

**"Alarm state trigger"**의 경우 **"In alarm"**으로 둡니다. 그 아래에서 **"Select an existing SNS topic"**을 선택합니다. 앞서 만든 **"CPU_Increase"**를 선택하고 **"Next"**를 누릅니다. 이제 알람에 이름을 지정해야 합니다. 간단하게 이름을 `ScaleDown-Alarm`으로 지정하고 **"Next"**를 누릅니다. 계속해서 단계를 검토하고 **"Create alarm"**를 누르는 것을 잊지 마세요.

> 방금 생성한 경보가 울릴 때 Auto Scaling 정책이 트리거되고 Auto Scaling 정책이 다시 적용되기 전에 AWS가 10분 (600 초)을 기다리도록 합니다.


이전에 있었던 "Create scaling policy" 탭으로 다시 전환하고 새로 고침 아이콘을 눌러 방금 생성한 `ScaleDown-Alarm` CloudWatch 경보를 찾습니다. "Take the Action"에서 **"Set to" "3" "capacity unit"**을 선택합니다. 마지막으로 **"seconds before allowing another scaling activity"** 를 **`600` **으로 설정하고 **"Create"**를 누릅니다.

![AWS Create scaling policy](/images/aws_create_scaling_policy_down.png)