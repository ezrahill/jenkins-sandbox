# Jenkins Sandbox
Repository for deploying Jenkins in multiple ways:

1. CloudFormation
2. Docker
3. Terraform

![Jenkins](jenkins.png)

## CloudFormation
To follow...

## Docker
To be ran locally on your workstation.
### Pre-requisites
- Docker Installed
- DOcker-Compose Installed

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