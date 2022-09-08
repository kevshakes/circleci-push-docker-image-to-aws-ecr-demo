# CI/CD Pipeline to Push Docker Image to a Private AWS ECR With CircleCI

## Build the Dockerfile

`docker build -t circleci-push-image-demo .`

## Install AWS CLI v2 and initialize

Follow instructions here https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions to get AWS CLI v2 installed.

`aws configure` and enter your credentials.

## Pushing image to AWS ECR

`$(aws ecr get-login --no-include-email --region eu-central-1)`

Build and push image to ECR:

`docker tag circleci-push-image-demo:latest <YOUR_AWS_ACC_ID>.dkr.ecr.eu-central-1.amazonaws.com/circleci-push-image-demo:latest`

`docker push <YOUR_AWS_ACC_ID>.dkr.ecr.eu-central-1.amazonaws.com/circleci-push-image-demo:latest`
