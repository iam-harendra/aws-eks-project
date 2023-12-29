# aws-eks-project
creating cluster using below command
 eksctl create cluster --name demo-cluster --region us-east-1 --fargate
 root@ip-172-31-21-231:/home/ubuntu# eksctl create cluster --name demo-cluster --region us-east-1 --fargate
2023-12-29 05:42:15 [ℹ]  eksctl version 0.167.0
2023-12-29 05:42:15 [ℹ]  using region us-east-1
2023-12-29 05:42:15 [ℹ]  setting availability zones to [us-east-1f us-east-1b]
2023-12-29 05:42:15 [ℹ]  subnets for us-east-1f - public:192.168.0.0/19 private:192.168.64.0/19
2023-12-29 05:42:15 [ℹ]  subnets for us-east-1b - public:192.168.32.0/19 private:192.168.96.0/19
2023-12-29 05:42:15 [ℹ]  using Kubernetes version 1.27
2023-12-29 05:42:15 [ℹ]  creating EKS cluster "demo-cluster" in "us-east-1" region with Fargate profile
2023-12-29 05:42:15 [ℹ]  if you encounter any issues, check CloudFormation console or try 'eksctl utils describe-stacks --region=us-east-1 --cluster=demo-cluster'
2023-12-29 05:42:15 [ℹ]  Kubernetes API endpoint access will use default of {publicAccess=true, privateAccess=false} for cluster "demo-cluster" in "us-east-1"
2023-12-29 05:42:15 [ℹ]  CloudWatch logging will not be enabled for cluster "demo-cluster" in "us-east-1"
2023-12-29 05:42:15 [ℹ]  you can enable it with 'eksctl utils update-cluster-logging --enable-types={SPECIFY-YOUR-LOG-TYPES-HERE (e.g. all)} --region=us-east-1 --cluster=demo-cluster'
2023-12-29 05:42:15 [ℹ]
2 sequential tasks: { create cluster control plane "demo-cluster",
    2 sequential sub-tasks: {
        wait for control plane to become ready,
        create fargate profiles,
    }
}
2023-12-29 05:42:15 [ℹ]  building cluster stack "eksctl-demo-cluster-cluster"
2023-12-29 05:42:16 [ℹ]  deploying stack "eksctl-demo-cluster-cluster"
2023-12-29 05:42:46 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
 2023-12-29 05:43:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:44:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:45:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:46:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:47:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:48:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:49:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:50:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:51:16 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-cluster"
2023-12-29 05:53:18 [ℹ]  creating Fargate profile "fp-default" on EKS cluster "demo-cluster"
2023-12-29 05:57:36 [ℹ]  created Fargate profile "fp-default" on EKS cluster "demo-cluster"
2023-12-29 05:58:06 [ℹ]  "coredns" is now schedulable onto Fargate
2023-12-29 05:59:09 [ℹ]  "coredns" is now scheduled onto Fargate
2023-12-29 05:59:09 [ℹ]  "coredns" pods are now scheduled onto Fargate
2023-12-29 05:59:09 [ℹ]  waiting for the control plane to become ready
2023-12-29 05:59:12 [✔]  saved kubeconfig as "/root/.kube/config"
2023-12-29 05:59:12 [ℹ]  no tasks
2023-12-29 05:59:12 [✔]  all EKS cluster resources for "demo-cluster" have been created
2023-12-29 05:59:15 [ℹ]  kubectl command should work with "/root/.kube/config", try 'kubectl get nodes'
2023-12-29 05:59:15 [✔]  EKS cluster "demo-cluster" in "us-east-1" region is ready
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#

![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/b6c57029-e030-4d58-a76f-27331dc0bf75)
click on created cluster for overview
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/ac5767d0-1b9d-4086-8ce0-f63a31b08cd8)
check the resources
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/6fc0062f-e101-40de-876d-836e4ec32455)
OIDC OpenID Connect provider URL
https://oidc.eks.us-east-1.amazonaws.com/id/B10FE18FB12B6621890BCD5E49118205
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/865576e3-a78b-4bc2-b16c-b556a412a212)
we can check the instance type like EC2, fargate
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/ca34c55d-994c-4ce9-91ad-561aea2beb69)
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/356339af-dcae-4ab8-8314-54a1ccac87f6)
  create the fargate profile(LIKE NODE AFFINITY IN K8S) using below command
  eksctl create fargateprofile \
    --cluster demo-cluster \
    --region us-east-1 \
    --name alb-sample-app \
    --namespace game-2048
    GUI SCREENSHOT
    ![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/c6aa9631-b982-4145-807e-74e0362fbec6)
    cli logs
    root@ip-172-31-21-231:/home/ubuntu# eksctl create fargateprofile \
    --cluster demo-cluster \
    --region us-east-1 \
    --name alb-sample-app \
    --namespace game-2048
2023-12-29 06:30:53 [ℹ]  creating Fargate profile "alb-sample-app" on EKS cluster "demo-cluster"
        2023-12-29 06:35:11 [ℹ]  created Fargate profile "alb-sample-app" on EKS cluster "demo-cluster"
root@ip-172-31-21-231:/home/ubuntu#

DEPLOY THE APPLICATION USING BELOW COMMAND
kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/examples/2048/2048_full.yaml
CLI LOGS
root@ip-172-31-21-231:/home/ubuntu# kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/examples/2048/2048_full.yaml
namespace/game-2048 created
deployment.apps/deployment-2048 created
service/service-2048 created
ingress.networking.k8s.io/ingress-2048 created
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
BEFORE INSTALLING THE ALB , CONFIGURE THE OIDC
CLI LOGS
root@ip-172-31-21-231:/home/ubuntu# eksctl utils associate-iam-oidc-provider --cluster demo-cluster --approve
2023-12-29 06:46:53 [ℹ]  will create IAM Open ID Connect provider for cluster "demo-cluster" in "us-east-1"
2023-12-29 06:46:53 [✔]  created IAM Open ID Connect provider for cluster "demo-cluster" in "us-east-1"
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
INSTALL THE ALB TO ACCESS THE APPLICATION
first download the IAM policy and create the IAM policy
root@ip-172-31-21-231:/home/ubuntu# curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  8386  100  8386    0     0  35853      0 --:--:-- --:--:-- --:--:-- 35991
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# aws iam create-policy \
    --policy-name AWSLoadBalancerControllerIAMPolicy \
    --policy-document file://iam_policy.json
{
    "Policy": {
        "PolicyName": "AWSLoadBalancerControllerIAMPolicy",
        "PolicyId": "ANPA3RGRJPAEIBJ2NMR3R",
        "Arn": "arn:aws:iam::792860391432:policy/AWSLoadBalancerControllerIAMPolicy",
        "Path": "/",
        "DefaultVersionId": "v1",
        "AttachmentCount": 0,
        "PermissionsBoundaryUsageCount": 0,
        "IsAttachable": true,
        "CreateDate": "2023-12-29T06:50:30+00:00",
        "UpdateDate": "2023-12-29T06:50:30+00:00"
    }
}
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
CREATE IAM role
  eksctl create iamserviceaccount \
  --cluster=<your-cluster-name> \
  --namespace=kube-system \
  --name=aws-load-balancer-controller \
  --role-name AmazonEKSLoadBalancerControllerRole \
  --attach-policy-arn=arn:aws:iam::<your-aws-account-id>:policy/AWSLoadBalancerControllerIAMPolicy \
  --approve
  chnage the AWS ACCOUNT ID
  CLI LOGS
  root@ip-172-31-21-231:/home/ubuntu# eksctl create iamserviceaccount \
  --cluster=demo-cluster \
  --namespace=kube-system \
  --name=aws-load-balancer-controller \
  --role-name AmazonEKSLoadBalancerControllerRole \
  --attach-policy-arn=arn:aws:iam::7928-6039-1432:policy/AWSLoadBalancerControllerIAMPolicy \
  --approve
2023-12-29 06:56:40 [ℹ]  1 iamserviceaccount (kube-system/aws-load-balancer-controller) was included (based on the include/exclude rules)
2023-12-29 06:56:40 [!]  serviceaccounts that exist in Kubernetes will be excluded, use --override-existing-serviceaccounts to override
2023-12-29 06:56:40 [ℹ]  1 task: {
    2 sequential sub-tasks: {
        create IAM role for serviceaccount "kube-system/aws-load-balancer-controller",
        create serviceaccount "kube-system/aws-load-balancer-controller",
    } }2023-12-29 06:56:40 [ℹ]  building iamserviceaccount stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 06:56:40 [ℹ]  deploying stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 06:56:40 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 06:57:10 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 06:57:10 [ℹ]  1 error(s) occurred and IAM Role stacks haven't been created properly, you may wish to check CloudFormation console
2023-12-29 06:57:10 [✖]  waiter state transitioned to Failure
Error: failed to create iamserviceaccount(s)
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# eksctl create iamserviceaccount   --cluster=demo-cluster   --namespace=kube-system   --name=aws-load-balancer-controller   --role-name AmazonEKSLoadBalancerControllerRole   --attach-policy-arn=arn:aws:iam::7928-6039-1432:policy/AWSLoadBalancerControllerIAMPolicy   --approve
2023-12-29 06:57:59 [ℹ]  1 existing iamserviceaccount(s) (kube-system/aws-load-balancer-controller) will be excluded
2023-12-29 06:57:59 [ℹ]  1 iamserviceaccount (kube-system/aws-load-balancer-controller) was excluded (based on the include/exclude rules)
2023-12-29 06:57:59 [!]  serviceaccounts that exist in Kubernetes will be excluded, use --override-existing-serviceaccounts to override
2023-12-29 06:57:59 [ℹ]  no tasks
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
ADD HELM
root@ip-172-31-21-231:/home/ubuntu# helm repo add eks https://aws.github.io/eks-charts
Command 'helm' not found, but can be installed with:
snap install helm
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# snap install helm
error: This revision of snap "helm" was published using classic confinement and thus may perform
       arbitrary system changes outside of the security sandbox that snaps are usually confined to,
       which may put your system at risk.

       If you understand and want to proceed repeat the command including --classic.
root@ip-172-31-21-231:/home/ubuntu# snap install helm --classic
helm 3.10.1 from Snapcrafters✪ installed
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# helm repo add eks https://aws.github.io/eks-charts
"eks" has been added to your repositories
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
ALB INSTALLED
root@ip-172-31-21-231:/home/ubuntu# helm install aws-load-balancer-controller eks/aws-load-balancer-controller \
  -n kube-system \
  --set clusterName=demo-cluster \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller \
  --set region=us-east-1 \
  --set vpcId=vpc-021fdeb613bee5f21
Error: INSTALLATION FAILED: expected at most two arguments, unexpected arguments:
-n: command not found
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system \
  --set clusterName=demo-cluster \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller \
  --set region=us-east-1 \
  --set vpcId=vpc-021fdeb613bee5f21
NAME: aws-load-balancer-controller
LAST DEPLOYED: Fri Dec 29 07:07:41 2023
NAMESPACE: kube-system
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
AWS Load Balancer controller installed!
root@ip-172-31-21-231:/home/ubuntu#

CHECK THE STACK IN CLOUD FORMATION
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/fd0eaee9-faf4-46bc-bf51-5c29532db907)
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/3d34fbd6-b499-4889-bfb5-22ff05eb9472)

NOT ABLE TO FIND DEPLOYMENT IN KUBE-SYSTEM 
root@ip-172-31-21-231:/home/ubuntu# helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system \
  --set clusterName=demo-cluster \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller \
  --set region=us-east-1 \
  --set vpcId=vpc-021fdeb613bee5f21
NAME: aws-load-balancer-controller
LAST DEPLOYED: Fri Dec 29 07:53:23 2023
NAMESPACE: kube-system
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
AWS Load Balancer controller installed!
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# helm ls
NAME    NAMESPACE       REVISION        UPDATED STATUS  CHART   APP VERSION
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# kubectl get deployment
NAME                          READY   UP-TO-DATE   AVAILABLE   AGE
eks-sample-linux-deployment   3/3     3            3           38m
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu# kubectl get deployment aws-load-balancer-controller
Error from server (NotFound): deployments.apps "aws-load-balancer-controller" not found
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
 LOAD BALANCER IS NOT PRESENT IN EC2
 ![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/4d0b3d43-356a-47fc-82e5-51bd9381c8c8)
 ABHISHEK OUTPUT
 ![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/6239ab24-1521-44ef-bcfe-db936ed68bd4)
 DELETING THE CLUSTER
 root@ip-172-31-21-231:/home/ubuntu# eksctl delete cluster --name demo-cluster --region us-east-1
2023-12-29 08:12:08 [ℹ]  deleting EKS cluster "demo-cluster"
2023-12-29 08:12:10 [ℹ]  deleting Fargate profile "alb-sample-app"
2023-12-29 08:16:32 [ℹ]  deleted Fargate profile "alb-sample-app"
2023-12-29 08:16:32 [ℹ]  deleting Fargate profile "fp-default"
2023-12-29 08:18:41 [ℹ]  deleted Fargate profile "fp-default"
2023-12-29 08:18:41 [ℹ]  deleted 2 Fargate profile(s)
2023-12-29 08:18:42 [✔]  kubeconfig has been updated
2023-12-29 08:18:42 [ℹ]  cleaning up AWS load balancers created by Kubernetes objects of Kind Service or Ingress
2023-12-29 08:18:43 [ℹ]
2 sequential tasks: {
    2 sequential sub-tasks: {
        2 sequential sub-tasks: {
            delete IAM role for serviceaccount "kube-system/aws-load-balancer-controller",
            delete serviceaccount "kube-system/aws-load-balancer-controller",
        },
        delete IAM OIDC provider,
    }, delete cluster control plane "demo-cluster" [async]
}
2023-12-29 08:18:43 [ℹ]  will delete stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 08:18:43 [ℹ]  waiting for stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller" to get deleted
2023-12-29 08:18:43 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 08:19:13 [ℹ]  waiting for CloudFormation stack "eksctl-demo-cluster-addon-iamserviceaccount-kube-system-aws-load-balancer-controller"
2023-12-29 08:19:14 [ℹ]  deleted serviceaccount "kube-system/aws-load-balancer-controller"
2023-12-29 08:19:14 [ℹ]  will delete stack "eksctl-demo-cluster-cluster"
2023-12-29 08:19:14 [✔]  all cluster resources were deleted
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#
root@ip-172-31-21-231:/home/ubuntu#

CLUSTER IS DELETED
![image](https://github.com/iam-harendra/aws-eks-project/assets/96298529/4f58d543-28ca-4e50-abbc-805a97bf4a7f)















