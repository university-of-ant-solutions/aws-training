
### To setup ECS, follow this steps

- Setup phase

1. Setup iam roles (AmazonEC2ContainerServiceforEC2Role)

2. Create a Ecs Cluster

3. Create a Security Group

4. Launch Autoscaling Group

- Deploy phase

5. Setup ALB

6. Update Task Definition

7. Update ECS Service

### TODOS

Delete old images in ECR

- IMAGES=$(aws ecr list-images --repository-name ${REPOSITORY_NAME}-build-tool --query 'imageIds[?type(imageTag)!=`string`].[imageDigest]' --output text)
- echo $IMAGES
