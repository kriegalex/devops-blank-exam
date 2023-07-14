# DevOps technical interview

## Technical interview questions - Coding

1. **Dockerfile Creation**
   ```
   FROM alpine:latest
   RUN apk add --update nodejs nodejs-npm
   WORKDIR /app
   COPY . .
   RUN echo "console.log('Hello, World!');" > index.js
   CMD ["node", "index.js"]
   ```
   This Dockerfile starts from the alpine:latest base image, installs Node.js and npm, sets the working directory to /app, copies the current directory into the Docker image, creates a simple "Hello, World!" Node.js application, and sets the default command to run the application.
2. **Ansible Playbook Creation**
   ```
   ---
   - hosts: webservers
   become: yes
   tasks:
      - name: Install Nginx
         apt:
         name: nginx
         state: present
      - name: Start Nginx
         service:
         name: nginx
         state: started
      - name: Create index.html
         copy:
         content: "Hello, World!"
         dest: /var/www/html/index.html
   ```
   This Ansible playbook installs Nginx on the web servers, ensures that the Nginx service is running, and creates an index.html file with the content "Hello, World!".
3. **Terraform Script Creation**
   - AWS
   ```
   provider "aws" {
      region = "us-west-2"
   }

   resource "aws_s3_bucket" "bucket" {
      bucket = "unique-name"
      acl    = "private"
   }
   ```
   This Terraform script creates an AWS S3 bucket with a unique name in the us-west-2 region.
   - Google Cloud
   ```
   provider "google" {
      project = "your_project_id"
      region  = "us-central1"
   }

   resource "google_storage_bucket" "bucket" {
      name     = "unique-name"
      location = "US"
   }
   ```
   This Terraform script creates a Google Cloud Storage bucket with a unique name in the US location.
   - Microsoft Azure
   ```
   provider "azurerm" {
      features {}
   }

   resource "azurerm_resource_group" "example" {
      name     = "unique-name"
      location = "West Europe"
   }

   resource "azurerm_storage_account" "example" {
      name                     = "uniquestoragename"
      resource_group_name      = azurerm_resource_group.example.name
      location                 = azurerm_resource_group.example.location
      account_tier             = "Standard"
      account_replication_type = "GRS"
   }

   resource "azurerm_storage_container" "example" {
      name                  = "unique-name"
      storage_account_name  = azurerm_storage_account.example.name
      container_access_type = "private"
   }
   ```
   This Terraform script creates an Azure Blob Storage container with a unique name in the West Europe location.
   - Exoscale
   ```
   provider "exoscale" {}

   resource "exoscale_sos_bucket" "bucket" {
      name = "unique-name"
      zone = "ch-dk-2"
   }
   ```
   This Terraform script creates an Exoscale Object Storage bucket with a unique name in the ch-dk-2 zone.

4. **CI/CD Pipeline Creation**
   - Jenkins
   ```
   pipeline {
      agent any

      stages {
         stage('Build') {
               steps {
                  echo 'Building..'
               }
         }
         stage('Test'){
               steps {
                  echo 'Testing..'
               }
         }
         stage('Deploy') {
               steps {
                  echo 'Deploying....'
               }
         }
      }
   }
   ```
   This Jenkinsfile defines a simple CI/CD pipeline with three stages: Build, Test, and Deploy. In each stage, it simply prints a message to the console.
   - Gitlab
   ```
   stages:
      - build
      - test
      - deploy

   build:
      stage: build
      script:
         - echo 'Building..'

   test:
      stage: test
      script: 
         - echo 'Testing..'

   deploy:
      stage: deploy
      script: 
         - echo 'Deploying....'
   ```
   This .gitlab-ci.yml file defines a simple CI/CD pipeline with three stages: Build, Test, and Deploy. In each stage, it simply prints a message to the console.
   - Github
   ```
   name: CI/CD Pipeline

   on: [push]

   jobs:
   build:
      runs-on: ubuntu-latest
      steps:
         - name: Build
         run: echo 'Building..'

   test:
      runs-on: ubuntu-latest
      steps:
         - name: Test
         run: echo 'Testing..'

   deploy:
      runs-on: ubuntu-latest
      steps:
         - name: Deploy
         run: echo 'Deploying....'
   ```
   This .github/workflows/main.yml file defines a simple CI/CD pipeline with three jobs: Build, Test, and Deploy. In each job, it simply prints a message to the console.
   - CircleCI
   ```
   version: 2.1
   jobs:
   build:
      docker:
         - image: circleci/python:3.7
      steps:
         - run: echo 'Building..'
   test:
      docker:
         - image: circleci/python:3.7
      steps:
         - run: echo 'Testing..'
   deploy:
      docker:
         - image: circleci/python:3.7
      steps:
         - run: echo 'Deploying....'

   workflows:
   version: 2
   build-test-deploy:
      jobs:
         - build
         - test
         - deploy
   ```
   This .circleci/config.yml file defines a simple CI/CD pipeline with three jobs: Build, Test, and Deploy. In each job, it simply prints a message to the console.

   In each of these examples, the pipeline is triggered on every push to the repository. The exact trigger conditions can be customized according to your needs.

5. **Kubernetes YAML File Creation**
   ```
   apiVersion: apps/v1
   kind: Deployment
   metadata:
   name: hello-world
   spec:
   replicas: 2
   selector:
      matchLabels:
         app: hello-world
   template:
      metadata:
         labels:
         app: hello-world
      spec:
         containers:
         - name: hello-world
         image: nginx
         ports:
         - containerPort: 80
   ```
   This Kubernetes YAML file defines a Deployment for a simple "Hello, World!" application using the Nginx image. The Deployment creates two replicas of the pod.