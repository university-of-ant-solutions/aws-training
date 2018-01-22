
### What is ECS ?

Amazon EC2 Container Service (Amazon ECS) is a highly scalable, fast, container management service that makes it easy to run, stop, and manage Docker containers on a cluster of Amazon Elastic Compute Cloud (Amazon EC2) instances. 

### ECS Clusters

An Amazon ECS cluster is a logical grouping of container instances that you can place tasks on.

Cluster Concepts:

- Clusters can contain multiple different container instance types.
- Clusters are region-specific.
- Container instances can only be a part of one cluster at a time.
- You can create custom IAM policies for your clusters to allow or restrict users' access to specific clusters.

### ECS Container Agent

The Amazon ECS container agent allows container instances to connect to your cluster. 

### Task Definitions

The task definition is a text file in JSON format that describes one or more containers that form your application. It can be thought of as a blueprint for your application.

Some of the parameters you can specify in a task definition include:

Which Docker images to use with the containers in your task
How much CPU and memory to use with each container
Whether containers are linked together in a task
The Docker networking mode to use for the containers in your task
What (if any) ports from the container are mapped to the host container instance
Whether the task should continue to run if the container finishes or fails
The command the container should run when it is started
What (if any) environment variables should be passed to the container when it starts
Any data volumes that should be used with the containers in the task
What (if any) IAM role your tasks should use for permissions

### Services

Amazon ECS allows you to run and maintain a specified number (the "desired count") of instances of a task definition simultaneously in an ECS cluster. This is called a service. If any of your tasks should fail or stop for any reason, the Amazon ECS service scheduler launches another instance of your task definition to replace it and maintain the desired count of tasks in the service.
