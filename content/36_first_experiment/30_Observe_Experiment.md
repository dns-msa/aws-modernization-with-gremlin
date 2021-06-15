+++
title = "2.4 실험 관찰"
chapter = true
weight = 30
+++
# 2.4 실험 관찰
## 실험 관찰

이제 공격을 시작했으므로 [Container Insights](https://console.aws.amazon.com/cloudwatch/home?region=us-west-2#container-insights:performance)로 다시 전환하여 카오스를 관찰합니다. 방금 시작한 실험에서 CPU 사용률이 급증한 것을 확인할 수 있도록 사용자 지정 시간 프레임으로 자유롭게 변경하십시오.

##### 가설이 맞습니까?
##### CPU가 증가 했습니까?
##### Auto-Scaling이 시작 되었습니까?
##### 자동 확장 정책을 설정한 사람이 있습니까?


## 결과 

![Container Insights Results](/images/container_insights_exp1_results.png)

Container Insights의 **CPU Utilization** 그래프에서 CPU 스파이크가 나타났지만 **Number of Nodes**에 대한 그래프는 증가하지 않았습니다.

![Container Insights Results](/images/container_insights_exp1_results2.png) 

**Auto-Scaling을 설정하고 확인하는 작업 항목을 만들 것입니다.**