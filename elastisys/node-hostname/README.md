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
        package.json
/// Added the ejs dependency
        apps.js
/// Added the following to eliminate error message ///
app.set('view engine', 'ejs');
//////////////////////////////////////////////////////
        index.js
/// For the bonus Rolling Update added the following string value
    str: "Hello Elastisys! - by Andreas Stylianou"
//////////////////////////////////////////////////////

### 2. Build and Push the Image
 docker image build -t node-docker-app . 
 docker image tag node-docker-app astylacr.azurecr.io/node-docker-app:v2
 docker push astylacr.azurecr.io/node-docker-app:v2
### 4. Build a yaml file and Deploying to AKS
 cd AKSDeploy
 kubectl apply -f deploy.yaml --dry-run     
 kubectl apply -f deploy.yaml 
### 5. Access the Application
https://aksnginx.magpie.gr/
You should receive the following json 
{"hostname":"nodeapp-58b54b55c7-n5wr6","version":"0.0.1","str":"Hello Elastisys! - by Andreas Stylianou"}

https://aksnginx.magpie.gr/users
You should receive the following string that simulates a response with some data
"respond with a resource"

https://aksnginx.magpie.gr/crash
You should receive an error message - this endpoint simulates a crash that forces the container to 
terminate

### 6. Helm Chart
You can find the Helm Chart in the helmChart folder. 
Configured with Ingress Controller and ACME Certificate Manager for Let's Encrypt TLS certificates
### 7. GitHub Actions Workflow
Created a Build and Deploy Workflow

 

