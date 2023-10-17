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
  o	GitHub Account
  o	Sign up for Terraform Cloud
  o	Install the AWS CLI
  o	Sign up for an AWS Account
  o	Your preferred IDE (I used AWS Cloud9)
  o	Install Terraform
  o	AWS EC2 key Pair


