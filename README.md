# Udagram
## Overview
This is an Infrastructure as Code project. The project deploys a high-availability web app by using AWS CloudFormation.

## Structure
The web app uses an EC2 load balancer to divert network traffic to multiple EC2 instances. There is a load auto scaling service creates and destories the instances on demand. All the infrastructures have copies in another availibility zone, which provides the web app a very high availability.

Infrastructure Diagram:

![Infrastructure Diagram](https://github.com/brianx0215/Udagram/blob/main/infra_diagram.png "Infrastructure Diagram")

## How to Use
### Prerequest
Make sure [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html) is installed on your server

Make sure you have enough limit to create the infrastructures.

### Configuration
Go to [IAM user pannel](https://console.aws.amazon.com/iam/home?#/users) and create a user with access key. Go back to the command line and type `aws configure` , paste the access key info into dialog

Go to [IAM role pannel](https://console.aws.amazon.com/iam/home?#/roles) and create a role named `UdacityS3ReadOnlyEC2` attached with policy `AmazonS3ReadOnlyAccess`

### Run the script
`./create_stack.sh {STACK NAME} infra.yaml infra_parameter.json {REGION}`

An Example:
`./create_stack.sh Udagram infra.yaml infra_parameter.json us-west-1`