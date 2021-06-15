+++
title = "Cleanup"
chapter = false
weight = 10
+++

### Cleanup 
In order to prevent charges to your account we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges.



```bash
# Detach IAM policy for CloudWatch ContainerInsights
aws iam detach-role-policy \
  --role-name $ROLE_NAME \
  --policy-arn arn:aws:iam::aws:policy/CloudWatchAgentServerPolicy

# Delete EKS cluster
eksctl delete cluster --name sockshop-eks-cluster --region $AWS_REGION

echo 'Completed cleanup..'
```



