+++
title = "1.1 클러스터 생성"
chapter = true
weight = 01
+++

# eksctl 클러스터 생성 


[eksctl](https://eksctl.io/introduction/)을 사용하면 EKS에서 Kubernetes 클러스터를 간편하게 프로비저닝 할 수 있습니다. 이 워크숍에서는 기본 2 노드 EKS 클러스터를 생성합니다. `eksctl` 을 사용하면 단일 명령줄입니다.


```
eksctl create cluster --name sockshop-eks-cluster \
  --version 1.20 --region $AWS_REGION \
  --nodegroup-name standard-workers --node-type t3.medium \
  --nodes 2 --nodes-min 1 --nodes-max 3 \
  --enable-ssm
```

`kubeconfig` 메시지로 끝나는 여러 메시지가 스크롤되는 것을 볼 수 있습니다.

<pre>
[ℹ]  waiting for at least 1 node(s) to become ready in "standard-workers"
[ℹ]  nodegroup "standard-workers" has 3 node(s)
[ℹ]  node "ip-192-168-4-140.us-west-2.compute.internal" is not ready
[ℹ]  node "ip-192-168-44-26.us-west-2.compute.internal" is not ready
[ℹ]  node "ip-192-168-79-117.us-west-2.compute.internal" is ready
[ℹ]  kubectl command should work with "/home/ec2-user/.kube/config", try 'kubectl get nodes'
[✔]  EKS cluster "sockshop-eks-cluster" in "us-west-2" region is ready
</pre>
