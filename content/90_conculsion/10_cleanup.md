+++
title = "클린업"
chapter = false
weight = 10
+++

### 클린업 
AWS 계정에 대한 비용 청구를 방지하려면 생성된 인프라를 정리하는 것이 좋습니다. 작업을 계속 진행하여 워크숍을 좀 더 살펴볼 계획이라면 작업이 끝난 후 정리 작업을 수행하는 것을 잊지 마십시오. AWS 계정에서 실행중인 작업을 그대로두고 잊어 버린다면 추가적인 비용이 발생 할 수 있습니다.



```bash
# Detach IAM policy for CloudWatch ContainerInsights
aws iam detach-role-policy \
  --role-name $ROLE_NAME \
  --policy-arn arn:aws:iam::aws:policy/CloudWatchAgentServerPolicy

# Delete EKS cluster
eksctl delete cluster --name sockshop-eks-cluster --region $AWS_REGION

echo 'Completed cleanup..'
```



