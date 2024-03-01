
# Introduction

In this project, I work on an Azure Virtual Machine to set up the environment. The setup process involves:

1. Installing all dependencies, including Git, Jenkins, Docker, Azure CLI, Helm, Kubernetes and Maven.
2. Creating a script to generate Azure Kubernetes Service (AKS) and Azure Container Registry (ACR), as well as a new namespace for deploying our application.
3. Configuring Jenkins by:
  - First, adding new plugins: Docker and Docker pipeline.
  - Second, creating new credentials to connect to ACR using a username and password.
  - Third, installing the Maven3 tool.
4. Developing a Dockerfile.
5. Executing the script.
6. Crafting a Helm chart and modifying files to tailor them to your application:
  - Adjusting the repository and service type in the values.yml file.
  - Altering the port in the template/deployments.yml file.

Following these steps, we proceed to work in Jenkins to create a pipeline that will build our image and push it to ACR. Subsequently, we will deploy the Helm chart to create new pods for our Spring Boot application. The deployment can be verified on a virtual machine.

Version of the dependecies that I use:
![image](https://github.com/florinelamuscalu/AKS-SpringBoot-App/assets/62910673/badce13a-cb0f-4388-a6ca-04684d9836fd)

Namespace of helm list of deployments
![image](https://github.com/florinelamuscalu/AKS-SpringBoot-App/assets/62910673/e7e361c6-d5a1-4832-aa12-67b733e69a93)


Kubernetes pods and service 
![image](https://github.com/florinelamuscalu/AKS-SpringBoot-App/assets/62910673/6ca71e89-fb0e-4904-afb9-b45ec3395d9e)

The app: 
![image](https://github.com/florinelamuscalu/AKS-SpringBoot-App/assets/62910673/99727b43-cb03-4b72-ac67-6bf2eafe5fea)
