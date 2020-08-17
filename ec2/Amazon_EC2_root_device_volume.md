The root device volume contains the image used to boot the instance. 
We recommend you use AMIs backed by Amazon EBS, because they launch faster and use persistent storage.

## Root device storage concepts
EBS를 사용하라고 하니, 그에대한 설명만 요약하겠다.  
### Amazon EBS-backed instances
Instances that use Amazon EBS for the root device automatically have an Amazon EBS volume attached.(Amazon EBS snapshot referenced by the AMI you use)  
<br />
![ebs backed instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/ebs_backed_instance.png)
<br />
