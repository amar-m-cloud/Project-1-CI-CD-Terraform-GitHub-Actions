# Deploying A Two-Tier Architecture Using Terraform Cloud CI/CD

**INTRODUCTION:**

In the dynamic landscape of modern cloud computing, Infrastructure as Code (IaC) has emerged as a pivotal paradigm to efficiently manage and deploy complex infrastructure. Terraform, developed by HashiCorp, stands out as a leading IaC tool, enabling users to define, provision, and manage infrastructure as code in a declarative and version-controlled manner.

This project embarks on a journey to explore the deployment of a Two-Tier Architecture, a common pattern in web applications, utilizing the powerful capabilities of Terraform. Going beyond mere infrastructure provisioning, we'll integrate Continuous Integration/Continuous Deployment (CI/CD) pipelines using Terraform Cloud. This CI/CD integration adds a layer of automation, ensuring consistent and reliable deployments while facilitating collaboration among development and operations teams.

**Requirements:**
1.	Create a highly available two-tier AWS architecture containing the following:
    -  3 Public Subnets
    -  3 Private Subnets
    -  Auto Scaling Group for Bastion Host
    -  Auto Scaling Group for Web Server
    -  Internet-facing Application Load Balancer targeting Web Server Auto Scaling Group
2.	Deploy this using Terraform Cloud as a CI/CD tool to check your build.
3.	Use module blocks for ease of use and re-usability.

**Prerequisites:**

    -    GitHub Account
    -    Sign up for Terraform Cloud
    -    Install the AWS CLI
    -    Sign up for an AWS Account
    -    Your preferred IDE (I used AWS Cloud9)
    -    Install Terraform
    -    AWS EC2 key Pair

**Our Infrastructure:**
We will be deploying a two-tier architecture in AWS with public and private subnets. We want to ensure that our Web Servers are not able to be accessed directly from the internet so we are placing them in our private subnets. Since our Web Servers are in private subnets, we have no way of SSHing into them directly so we are going to add a Bastion Host in an Auto Scaling group with the desired capacity of 1. That way if the Bastion Host goes down, a new one will be created. Being in a private subnet also prevents our Web Servers from being able to access the internet for updates, so a NAT gateway has been added. Please note that for this project we only included one NAT gateway to keep costs low, but for high availability, you would want to add a NAT gateway to the other public subnets as well. The final issue with the private subnets is that the internet needs to access our website. To solve this, we added an Application Load Balancer that is internet-facing to direct traffic to our Web Servers, which are also in an Auto Scaling group to ensure high availability. Right now, we just have the desired capacity of 2 but could add a target policy in the future that would have the Auto Scaling group expand and contract based on demand.

![image](https://github.com/amar-m-cloud/Project-1-CI-CD-Terraform-GitHub-Actions/assets/89722343/74340f33-4fe6-4100-9464-d221a8e2cd0e)

