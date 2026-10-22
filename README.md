# Cloud Labs

Small hands-on labs from my AWS and container learning. Each folder is self-contained and was torn down after testing.

## lambda-container

An AWS Lambda function packaged as a Docker image, built on the official Lambda Python base image. Tested locally with the runtime emulator, pushed to Amazon ECR, deployed with an execution role, and invoked from the CLI.

Note: build with `docker build --platform linux/amd64 --provenance=false` so Lambda accepts the image manifest.

## ecs-fargate-quickstart

Terraform for a single ECS Fargate task running a custom nginx image from ECR, with an IAM execution role, a CloudWatch log group, and a security group that allows only my IP on port 80.

Deploy with `terraform apply -var 'my_ip=YOUR_IP'` and remove everything with `terraform destroy`. Fargate bills per second while a task runs.

## Related projects

- [inventory-app](https://github.com/fiehna-hue/inventory-app): Flask and Postgres API with Docker Compose and a keyless GitHub Actions pipeline
- [inventory-infra](https://github.com/fiehna-hue/inventory-infra): production-style ECS Fargate, ALB and RDS stack in Terraform