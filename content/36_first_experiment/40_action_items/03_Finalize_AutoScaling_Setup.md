+++
title = "2.5.3 AutoScaling Up 설정"
chapter = true
weight = 03
+++


## Auto Scaling 설정: 

이전에 있었던 "Create scaling policy" 탭으로 다시 전환하고 새로 고침 아이콘을 눌러 방금 생성한 CloudWatch 경보를 찾습니다. "Take the Action"에서 **"Add" "1" "capacity unit"**를 선택합니다.
마지막으로 **"seconds before allowing another scaling activity"** 를 **`600`**로 설정합니다.
![AWS Create scaling policy](/images/aws_create_scaling_policy.png)

> 방금 생성한 경보가 울릴 때 Auto Scaling 정책이 트리거되고 Auto Scaling 정책이 다시 적용되기 전에 AWS가 10분(600 초)을 기다리도록 합니다.



