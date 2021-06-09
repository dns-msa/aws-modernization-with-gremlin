+++
title = "1.5 AWS Container Insight 설치"
chapter = false
weight = 25

+++

[Amazon CloudWatch Container Insight](https://docs.aws.amazon.com/ko_kr/AmazonCloudWatch/latest/monitoring/ContainerInsights.html) CloudWatch Container Insights를 사용하여 마이크로 서비스와 컨테이너화 된 애플리케이션에서 지표 및 로그를 수집, 집계 및 요약합니다. Container Insights는 Amazon EC2의 Amazon Elastic Container Service (Amazon ECS), Amazon Elastic Kubernetes Service (Amazon EKS) 및 Kubernetes 플랫폼에서 사용할 수 있습니다. Amazon ECS 지원에는 Fargate에 대한 지원이 포함됩니다.


터미널 명령 프롬프트에서 다음 명령을 입력하여 Container Inshight 설치를 위한 환경 변수를 가져옵니다.

```bash
STACK_NAME=$(eksctl get nodegroup --cluster sockshop-eks-cluster -o json | jq -r '.[].StackName')
ROLE_NAME=$(aws cloudformation describe-stack-resources --stack-name $STACK_NAME | jq -r '.StackResources[] | select(.ResourceType=="AWS::IAM::Role") | .PhysicalResourceId')
```

ROLE_NAME 환경 변수를 확인하십시오.

```bash
test -n "$ROLE_NAME" && echo ROLE_NAME is "$ROLE_NAME" || echo ROLE_NAME is not set
```

Container Insight에 대한 추가 IAM 정책을 연결합니다.

```bash
aws iam attach-role-policy \
  --role-name $ROLE_NAME \
  --policy-arn arn:aws:iam::aws:policy/CloudWatchAgentServerPolicy


```

ROLE_NAME에 대해 첨부된 정책 확인합니다.

```bash
aws iam list-attached-role-policies --role-name $ROLE_NAME | grep CloudWatchAgentServerPolicy || echo 'Policy not found'

```

Container Insight 설치합니다.

```bash
curl -s https://raw.githubusercontent.com/aws-samples/amazon-cloudwatch-container-insights/latest/k8s-deployment-manifest-templates/deployment-mode/daemonset/container-insights-monitoring/quickstart/cwagent-fluentd-quickstart.yaml | sed "s/{{cluster_name}}/sockshop-eks-cluster/;s/{{region_name}}/us-west-2/" | kubectl apply -f -
```

설치가 완료되었는지 확인하십시오.

```bash
kubectl -n amazon-cloudwatch get daemonsets
```


🎉 축하합니다. 클러스터에 Container Insight를 배포했습니다.


