## Instances and AMIs
AMI is a template that contains a software configuration. From an AMI, you launch an instance, which is a copy of the AMI running as a virtual server.  
![ami](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/architecture_ami_instance.png)

## Instances
An instance is a virtual server in the cloud. Its configuration at launch is a copy of the AMI that you specified when you launched the instance.

## Storage for your instance
The root device for your instance contains the image used to boot the instance. 

## AMIs
AWS publishes many AMIs that contain common software configurations for public use. You can also create your own custom AMI; doing so enables 
you to quickly and easily start new instances that have everything you need.  
All AMIs are categorized as either backed by Amazon EBS, which means that the root device for an instance launched from the AMI is an Amazon EBS volume, or
backed by instance store, which means that the root device for an instance launched from the AMI is an instance store volume created from a template stored in Amazon S3.  
