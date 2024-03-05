---
title: "What's IaC (Infrastructure as a Code) ???"
date: 2023-04-02T10:16:10+05:45
draft: false
toc: false
images:
tags:
  - cloud
  - automation
  - configuration management
  - server
  - devops
---
What's IaC (Infrastructure as a Code) ???
![IaC](https://miro.medium.com/v2/resize:fit:720/format:webp/1*7940BGBj6_soXpc9lqPpng.png)


**Introduction**
Have you ever setup a virtual machine? You might know about using an ISO file to load in Oracle Virtual Box, going through all the steps on by one to install the ISO on the Virtual Hard-Disk and that's a lot of time being wasted. Well, to save some time you might have backed up you VM (of course Virtual Machine) and used OVA to load your VM. Then what about setting hundredzzz of such machine. Ughhhhh, there are many manual steps required to do all these. This is what's called "Administrative Overhead".
What if, there is a way to write all the setup instruction in a code and you can execute that code to get your system as you wanted it. With this code, you can even spawn as many machines (infrastructure as you call it) just with some clicks and execution. That's exactly what "Infrastructure as a Code" does.

**Advantages of IAC**
Firstly, the whole infrastructure can be codified which is easily readable rather than looking at each configuration of the system itself.
Previously, you were required to install servers manually that only resulted in administrative overhead, expensive and inconsistency among the systems. IAC will do it with just a few clicks.
The code can be easily copied, edited and distributed among department such as developers and operations that helps in deploying, provisioning, monitoring and managing large infrastructure.
It can help deploy application's required servers, networks, databases, and other such infrastructure aligned with business policies consistently.

**Potential Disssad**
Infrastructure code should be audited properly before deploying as it can result in various security vulnerabilities. Similarly, secure storage of IaC must be done to avoid its theft or tampering with code. This single code contains the whole blueprint of your infrastructure which should always be kept confidential. ALWAYSSSS.
You might require learning other IAC tools that can be complex in the beginning but can create a learning curve but that's the way of life.
These codes should be version controlled and any issue with such code in deployment process could result in increasing in downtime of systems and application and nobody wants that for sure.

**Tools for IAC**

**Terraform**: Terraform is an open-source infrastructure as code (IaC) tool that allows you to automate the provisioning, configuration, and management of cloud-based or on-premises infrastructure resources.
HashiCorp TerraformIt provides a way to define, deploy, and manage infrastructure resources declaratively using configuration files, called Terraform files, which are written in a high-level, human-readable domain-specific language (DSL).
![hashicorp](https://miro.medium.com/v2/resize:fit:720/format:webp/0*GXXoXgrWG92Yslni.png)

**IaC in Action**

Let's say you want to create an Amazon Web Services (AWS) Elastic Compute Cloud (EC2), that's just a fancy name for Virtual Machine, using Terraform. Here's what the Terraform configuration file might look like:
![terraform-example](https://miro.medium.com/v2/resize:fit:640/format:webp/1*MtKUCr_8_VPm4B_SQ63XWA.png)

In this example, the provider block specifies that we're using AWS as the cloud provider, and that we want to create the resources in the us-west-2 region.
The resource block defines the actual resource we want to create, which is an EC2 instance. We give it a name (example) and specify the Amazon Machine Image (AMI) we want to use (ami-0c55b159cbfafe1f0), as well as the instance type (t2.micro). We also add a tag to give it a name (Name = "example-instance").
To create the EC2 instance, we would run the following command:
terraform apply
This command tells Terraform to read the configuration file, compare it to the current state of the infrastructure, and make any necessary changes to bring the infrastructure into the desired state. In this case, Terraform would create a new EC2 instance in the AWS account specified in the configuration file.
If we wanted to destroy the EC2 instance, we could run the following command:
terraform destroy

**Summary**:
Use IaC for smart work. peaceeeeee