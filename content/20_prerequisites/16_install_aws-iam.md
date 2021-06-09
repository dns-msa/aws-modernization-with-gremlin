+++
title = "AWS IAM 설치"
chapter = false
weight = 16

+++

Amazon EKS는 IAM을 사용하여 Kubernetes용 AWS IAM 인증자를 통해 Kubernetes 클러스터에 인증을 제공합니다. Kubernetes용 AWS IAM 인증자를 설치하고 이를 인증에 사용하도록 kubectl 구성 파일을 수정하여 Amazon EKS와 함께 작동하도록 stock kubectl 클라이언트를 구성 할 수 있습니다.

Cloud9에 aws-iam-authenticator를 설치하려면

Amazon S3에서 Amazon EKS 판매 aws-iam-authenticator 바이너리를 다운로드 합니다.


```
curl -o aws-iam-authenticator https://amazon-eks.s3.us-west-2.amazonaws.com/1.15.10/2020-02-22/bin/linux/amd64/aws-iam-authenticator
```

바이너리에 실행 권한을 적용합니다.

```
chmod +x ./aws-iam-authenticator
```

그리고 공통 디렉토리로 이동하십시오.

```
sudo mv ./aws-iam-authenticator /usr/local/bin
```

aws-iam-authenticator 바이너리가 작동하는지 테스트합니다.

```
aws-iam-authenticator help
```
