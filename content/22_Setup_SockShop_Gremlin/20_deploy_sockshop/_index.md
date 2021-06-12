+++
title = "1.2 SockShop 배포"
chapter = false
weight = 02

+++



 AWS에서 `kubeconfig` 를 가져와야하는 경우. 먼저 `eksctl` 을 사용하여 클러스터 이름을 검색하면 됩니다.
```
eksctl get clusters
```

그런 다음 AWS에서 `kubeconfig` 를 가져옵니다.
```
 aws eks --region us-west-2  update-kubeconfig --name sockshop-eks-cluster
```

이제 `kubectl` 을 사용하여 클러스터를 볼 수 있습니다.

```
kubectl get nodes
```

이제 sock shop를 배치 할 수 있습니다.

먼저 아래의 저장소를 clone 합니다.

```
git clone https://github.com/dns-msa/microservices-demo
```

cd 명령어를 사용해 `complete-demo.yaml` 파일이 있는 위치로 이동합니다.

```
cd microservices-demo/deploy/kubernetes
```

애플리케이션을 배포하기 전에 네임 스페이스 만듭니다.

```
kubectl create namespace sock-shop
```

애플리케이션 배포합니다.

```
kubectl apply -f complete-demo.yaml
```

`front-end-svc` 로드 밸런서를 배포합니다. (`deploy/kubernetes/manifests` 참조)

```
kubectl apply -f manifests/front-end-svc.yaml
```

`kubectl get svc front-end -n sock-shop` 명령어를 실행하면  `font-end` 의 `LoadBalancer` 주소를 확인 할 수 있고 `http`를 통해 80 포트로 접속할 수 있습니다.


🎉 축하합니다. 클러스터에 데모 애플리케이션을 배포했습니다.





