# NodeApp - by Andreas Stylianou
A small Demo Project that includes Debugging, Containerization and Deployment of a trivial js application.

## Things to be done...
### 1. Helm Chart
Test the Helm Chart 
you can use the following commands
helm install nodeapp .  --dry-run --debug
helm install nodeapp . 
helm upgrade -i nodeapp .
### 2. Autpomation 
Upload the project to a GitHub Repo
Create an automation WorkFlow for Building and Deploying the App
### 3. Visibility
Although the specific AKS Cluster is already configured  with monitoring features  (Azure Metrics, Prometheus and Grafana), a discussion with the client might require in-depth tuning of alarms, dashboards etc.
### 4. Policy
All AKS Clusters come with a set of predefined Policies. Many more can be added according to the application's needs.
### 5. Security
Tighten the sucurity of the cluster by applying a Service Mesh (Istio) if the client's budget allows it.


 
