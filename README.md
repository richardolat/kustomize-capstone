# Project Overview:
## This project focuses on deploying a web application in a Kubernetes environment using Kustomize for managing different environment configurations (development, staging, production). Additionally, the process integrates with a CI/CD pipeline using GitHub Actions.

##  Set Up the Project Directory
#### mkdir kustomize-capstone
![Screenshot 2025-01-09 045139](https://github.com/user-attachments/assets/adea4891-cf3f-463b-8c7f-6cd887e2a1dd)
#### cd kustomize-capstone
![Screenshot 2025-01-09 045159](https://github.com/user-attachments/assets/0c7ec62e-03b9-4c0c-a839-a2b891bc0e82)
## Create the necessary subdirectories: 'mkdir base'  'mkdir overlays'
![Screenshot 2025-01-09 045649](https://github.com/user-attachments/assets/a36b2864-ba32-48f9-bb8f-2ae4b091e6ff)




##  Define Base Configuration
#### cd base : 'touch deployment.yaml'  'service.yaml' 'kustomization.yaml'
![Screenshot 2025-01-09 050102](https://github.com/user-attachments/assets/34e10009-7be5-4aa4-8288-06330d4c2e79)

## Create Environment-Specific Overlays 
#### create environment for development: mkdir dev 'touch kustomization.yam' touch patch.yam'
#### create environment for staging: mkdir stage  'touch kustomization.yam' touch patch.yam'
#### create environment for production: mkdir prod   'touch kustomization.yam' touch patch.yam'
![Screenshot 2025-01-09 050511](https://github.com/user-attachments/assets/fbc00d26-04a1-460f-a960-d79c24a9a6db)
![Screenshot 2025-01-09 050619](https://github.com/user-attachments/assets/43ceb557-f0ba-411c-a61d-001059f3900f)
![Screenshot 2025-01-09 050847](https://github.com/user-attachments/assets/eb1afe10-56cd-4907-a81f-514d6f6ce00e)

## Initialize Git Repository
#### 'git init'
#### Create a .gitignore file to exclude unnecessary files: 'echo ".DS_Store" >> .gitignore'  'echo ".kube" >> .gitignore' 'git add .' 'git commit -m "Initial commit with base and overlay configurations"'
![Screenshot 2025-01-09 054220](https://github.com/user-attachments/assets/e9d8b008-d99b-476f-b27b-b26c89f361a2)

##  CI/CD Pipeline with GitHub Actions
#### create .github/workflows/deploy.yml
![Screenshot 2025-01-09 054404](https://github.com/user-attachments/assets/8085a768-3dc9-4303-ad61-da4a17d17a27)

## Deploying on Minikube
#### minikube start --driver=docker
![Screenshot 2025-01-09 055603](https://github.com/user-attachments/assets/9cc4f572-374e-49fe-8080-49fed69296c2)

##  Deploy Application on Minikube
kubectl apply -k overlays/...env
![Screenshot 2025-01-09 061244](https://github.com/user-attachments/assets/8dc3cf82-610e-4bd1-9d20-25fe8e928fb2)
#### Verify the deployment: 'kubectl get pods' 'kubectl get svc'
![Screenshot 2025-01-09 061515](https://github.com/user-attachments/assets/1a4e8155-c9ae-4ffc-8548-96fd0fff11f9)

## It opens the web page automatically 
![Screenshot 2025-01-09 061536](https://github.com/user-attachments/assets/0fa79450-b911-4cda-a6ef-8e53f144f7d6)

![image](https://github.com/user-attachments/assets/eb5e64ee-fbd7-4667-96ae-7a0874bcecb5)








## Brief Note 
##### Implementation strategy: Utilizing Kustomize to handle environment-specific configurations and advanced features such as transformers generators
#### This project uses a secret named KUBE_CONFIG and decodes it into the kubeconfig file using base64. 
![image](https://github.com/user-attachments/assets/85dec936-cd66-4a97-968d-d371df801276)


















