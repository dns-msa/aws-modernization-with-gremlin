+++
title = "1.5 Install AWS Container Insight"
chapter = false
weight = 25

+++

[Amazon CloudWatch Container Insight](https://docs.aws.amazon.com/ko_kr/AmazonCloudWatch/latest/monitoring/ContainerInsights.html) Use CloudWatch Container Insights to collect, aggregate, and summarize metrics and logs from your containerized applications and microservices. Container Insights is available for Amazon Elastic Container Service (Amazon ECS), Amazon Elastic Kubernetes Service (Amazon EKS), and Kubernetes platforms on Amazon EC2. Amazon ECS support includes support for Fargate.


At the terminal command prompt, enter the following command to get environment variables for Container Inshight installation:

```bash
STACK_NAME=$(eksctl get nodegroup --cluster sockshop-eks-cluster -o json | jq -r '.[].StackName')
ROLE_NAME=$(aws cloudformation describe-stack-resources --stack-name $STACK_NAME | jq -r '.StackResources[] | select(.ResourceType=="AWS::IAM::Role") | .PhysicalResourceId')
```

Check the ROLE_NAME environment variable:

```bash
test -n "$ROLE_NAME" && echo ROLE_NAME is "$ROLE_NAME" || echo ROLE_NAME is not set
```

Attach additional IAM policy for Container Insight.

```bash
aws iam attach-role-policy \
  --role-name $ROLE_NAME \
  --policy-arn arn:aws:iam::aws:policy/CloudWatchAgentServerPolicy


```

Confirm attached policies for the ROLE_NAME

```bash
aws iam list-attached-role-policies --role-name $ROLE_NAME | grep CloudWatchAgentServerPolicy || echo 'Policy not found'

```

Install Container Insight

```bash
curl -s https://raw.githubusercontent.com/aws-samples/amazon-cloudwatch-container-insights/latest/k8s-deployment-manifest-templates/deployment-mode/daemonset/container-insights-monitoring/quickstart/cwagent-fluentd-quickstart.yaml | sed "s/{{cluster_name}}/sockshop-eks-cluster/;s/{{region_name}}/us-west-2/" | kubectl apply -f -
```

Verify that the installation is complete.

```bash
kubectl -n amazon-cloudwatch get daemonsets
```


🎉 Congrats, you've deployed the Container Insight on your cluster.


