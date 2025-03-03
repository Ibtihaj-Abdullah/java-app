# Hello World Java Application

A simple Spring Boot application deployed to Amazon ECS using CircleCI.

## Prerequisites

- Java 11
- Maven
- Docker
- AWS Account
- CircleCI Account
- AWS CLI configured with appropriate credentials

## Local Development

1. Clone the repository
2. Build the application:
   ```bash
   mvn clean package
   ```
3. Run the application:
   ```bash
   java -jar target/hello-world-app-1.0-SNAPSHOT.jar
   ```

## AWS Setup

1. Create an ECR repository named `hello-world-app`
2. Create an ECS cluster named `hello-world-cluster`
3. Create an ECS service named `hello-world-app`
4. Configure the necessary IAM roles and policies

## CircleCI Setup

1. Connect your GitHub repository to CircleCI
2. Add the following environment variables in CircleCI:
   - AWS_ACCESS_KEY_ID
   - AWS_SECRET_ACCESS_KEY
   - AWS_DEFAULT_REGION

## Deployment

The application will be automatically built and deployed when you push to the main branch. The deployment process includes:

1. Building the application with Maven
2. Creating a Docker image
3. Pushing the image to Amazon ECR
4. Deploying the new image to Amazon ECS

## Testing

Once deployed, you can test the application by accessing:
```
http://<your-ecs-service-url>/
```

You should see the message: "Hello, World!" 