# NodeApp - by Andreas Stylianou
A small Demo Project that includes Debugging, Containerization and Deployment of a trivial js application.

---

## Prerequisites

- Docker
- Kubernetes cluster (kind, minikube, or any cloud provider)
- kubectl
- Helm v3

---

## Getting Started
### 1. Code correction
        apps.js
/// Added the following to eliminate error message ///
app.set('view engine', 'ejs');
//////////////////////////////////////////////////////
        index.js
/// For the bonus Rolling Update added the following string value
    str: "Hello Elastisys! - by Andreas Stylianou"

### 2. Build and Push the Image
 docker image build -t node-docker-app . 
 docker image tag node-docker-app astylacr.azurecr.io/node-docker-app:v2
 docker push astylacr.azurecr.io/node-docker-app:v2
### 3. Build a yaml file and Deploying to AKS
 cd AKSDeploy
 kubectl apply -f deploy.yaml --dry-run     
 kubectl apply -f deploy.yaml 
### 3. Access the Application
http://172.211.174.151/
You should receive the following json 
{"hostname":"nodeapp-5d47c9c9bf-l9rjg","str":"Hello Elastisys! - by Andreas Stylianou"}
### 4. Helm Chart
You can find the Helm Chart in the helmChart folder (It is not tested yet)

 
