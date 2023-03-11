# Jenkins Sandbox
Repository for deploying Jenkins in multiple ways:

1. CloudFormation
2. Docker
3. Terraform

![Jenkins](jenkins.png)

## CloudFormation
Deploy using GUI or via CLI

### Pre-requisites
- AWS Account
- AWS Subnet ID
- AWS VPC ID
- SSH Public Key

#### AWS CLI
```bash
$ aws cloudformation create-stack --stack-name Jenkins \
--template-body file://jenkins_master.yaml \
--capabilities CAPABILITY_IAM \
--parameters \
ParameterKey=JenkinsPort,ParameterValue=8080 \
ParameterKey=SSHLocation,ParameterValue=1.2.3.4/32 \
ParameterKey=InstanceTagName,ParameterValue=Jenkins \
ParameterKey=SubnetId,ParameterValue=subnet-12a3456b \
ParameterKey=VpcId,ParameterValue=vpc-a12345bc6789 \
ParameterKey=KeyPairPublicKey,ParameterValue="ssh-rsa AAA..... ezrahill@Ezra-MBP.thehackshop.local" \
--profile a-cloud-guru --region us-east-1
```

## Docker
To be ran locally on your workstation.
### Pre-requisites
- Docker Installed
- Docker-Compose Installed

Create the following environmental variables using the shell or by creating a `.env` file in the root of this cloned repository.

#### Shell
```bash
$ export JENKINS_ADMIN_USER=
$ export JENKINS_ADMIN_PASS=
```
#### .env File
```
JENKINS_ADMIN_ID=
JENKINS_ADMIN_PASSWORD=
```

### Execution
Making use of Docker Compose, we can simply run the below command which will build and run a docker image.

The Jenkins console can be accessed via `http://localhost:8080`

```bash
$ docker-compose up -d
```

## Terraform
To Follow...