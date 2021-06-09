+++
title = "1.3 sock shop 테스트"
chapter = true
weight = 22
+++

# Sock Shop 테스트

Sock-shop 배포되었는지 테스트하기 위해 로드 밸런서 DNS 이름을 가져와서 자체 브라우저에서 테스트 할 것입니다. 해당 설정에 대한 단계를 확인하세요.

- [New EC2 Experience](#if-you-are-using-the-new-ec2-experience-follow-this)
- [Older EC2 Experience](#if-you-are-using-the-older-ec2-experience-follow-this) 
- [Running this workshop on your own](#if-you-are-running-this-workshop-on-your-own-follow-this)




#### **New EC2 Experience**을 사용하는 경우 다음을 따르십시오.


**AWS 이벤트에서 실행중인 경우** [EC2 콘솔](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#Home:)을 방문하십시오. 배스천 호스트 EC2 인스턴스에 로그인합니다. 배스천 호스트의 이름은 **-bastion.**로 끝납니다 (예 : **mod-f679f4081e7d405c-bastion**).
![Bastion-ec2](/images/ec2_connect.png)

배스천 호스트를 찾고 "Actions" 드롭 다운을 사용하여 "Connect"을 선택한 다음 **EC2 Instance Connect**을 선택합니다.

다음 페이지에서 사용자 이름을 **root**에서 `ec2-user`로 변경하고 **Connect**를 누릅니다. 새 브라우저 탭이 열립니다.

![ec2-change-username](/images/ec2_change_user.png)

{{% notice tip %}}
AWS EC2 콘솔 탭을 열어 둡니다. 다시 사용하겠습니다.
{{% /notice %}}

콘솔 창에서 다음 명령을 실행하여 로드 밸런서 IP를 가져옵니다.

```
kubectl get svc -o wide -n sock-shop | grep LoadBalancer
```

터미널에서 로드 밸런서 DNS 이름을 복사하여 붙여 넣습니다.

![Bastion-lb](/images/LB-IP.png)

웹 브라우저에 붙여넣기만 하면 됩니다.

![Bastion-sock](/images/Browser-Sock.png)

{{% notice tip %}}
또한 오늘의 나머지 활동을 위해 sock shop 브라우저 탭을 열어 두십시오.
{{% /notice %}}

#### 이전 **EC2 Experience** 을 사용하는 경우 다음을 따르십시오.

![AWS - EC2 - Old Experience ](/images/aws_ec2_connect_1.png)

**AWS 이벤트에서 실행중인 경우** [EC2 콘솔](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#Home:)을 방문하십시오. 배스천 호스트 EC2 인스턴스에 로그인합니다. 배스천 호스트의 이름은 **-bastion.**로 끝납니다 (예 : **mod-f679f4081e7d405c-bastion**). 배스천 호스트를 찾아 **"Connect"**을 누르면 아래와 같은 팝업 화면이 표시됩니다.

![AWS - EC2 - Old Experience ](/images/aws_ec2_connect_2.png)

팝업에서 **EC2 Instance Connect**를 선택하면 새 브라우저 창이 열립니다.

{{% notice tip %}}
오늘의 나머지 활동을 위해 이 브라우저 창을 열어 두십시오.
{{% /notice %}}

콘솔 창에서 다음 명령을 실행하여 로드 밸런서 IP를 가져옵니다.

```
kubectl get svc -o wide -n sock-shop | grep LoadBalancer
```

터미널에서 로드 밸런서 DNS 이름을 복사하여 붙여 넣습니다.

![Bastion-lb](/images/LB-IP.png)

웹 브라우저에 붙여넣기만 하면 됩니다.

![Bastion-sock](/images/Browser-Sock.png)

{{% notice tip %}}
또한 오늘의 나머지 활동을 위해 sock shop 브라우저 탭을 열어 두십시오.
{{% /notice %}}

#### 이 workshop을 직접 실행하는 경우 다음을 따르십시오.
로드 밸러서 DNS 이름을 가져 오려면 cloud9 터미널에서 다음 명령을 실행합니다.

```
kubectl get svc -o wide -n sock-shop | grep LoadBalancer
```
웹 브라우저에 붙여넣기만 하면 됩니다.

{{% notice tip %}}
오늘의 나머지 활동을 위해 이 브라우저 탭을 열어 두십시오.
{{% /notice %}}
