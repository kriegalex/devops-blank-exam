# DevOps technical interview

## Technical interview questions - Analysis

### Question 1
This **Dockerfile** is used to create a Docker image for a Python Flask application. It starts from a base image python:3.8-slim-buster, sets the working directory to /app, copies the requirements.txt file from the current directory to the Docker image, installs the Python dependencies using pip3, copies the rest of the application code to the Docker image, and finally sets the default command to start the Flask application.

### Question 2
This **Ansible playbook** is used to manage Apache web servers. It ensures that Apache is at the latest version, writes the Apache configuration file using a template, and ensures that the Apache service is running. If the configuration file changes, it triggers a handler to restart Apache.

### Question 3
This **Terraform** script is used to create an **AWS EC2 instance** in the us-west-2 region. The instance type is t2.micro, and the Amazon Machine Image (AMI) ID is ami-0c55b159cbfafe1f0. The instance is tagged with the name "example-instance".

### Question 4
This **Jenkinsfile** defines a simple **CI/CD pipeline** with three stages: Build, Test, and Deploy. In each stage, it simply prints a message to the console. In a real-world scenario, each stage would contain steps to build, test, and deploy an application.

### Question 5
This **Kubernetes** YAML file defines a Deployment for an Nginx application. It creates three replicas of the Nginx pod, each running the nginx:1.14.2 Docker image and exposing port 80.