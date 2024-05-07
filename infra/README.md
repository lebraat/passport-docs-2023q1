# infra

### New Stack

```
pulumi stack init gitcoin/dpopp/stackName
```

### AWS Configuration

```
# set aws profile credentials
aws configure --profile user1
```

_Note_ you will also need to select this profile in your env:

```
export AWS_PROFILE=user1
```

### Configure environment

Before we can run `pulumi up`, there are a few resources that need to be built/pushed to the aws environment, such as the secret manager, Route53 Hosted Zone, and iam-server docker image. Once these are present on aws, we must reference them in our local environment in order for pulumi to be aware of them:

```
# set route53 zone
export ROUTE_53_ZONE=...
# set environment-sepecific domain
export DOMAIN=...
# secrets manager resource ARN
export IAM_SERVER_SSM_ARN=...
# iam-server docker image in ECR
export DOCKER_GTC_PASSPORT_IAM_IMAGE=...
```

### Pulumi deploy

```
pulumi up
```
