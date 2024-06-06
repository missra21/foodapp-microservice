# foodapp-microservice

## Steps to deploy

```
kubectl apply -f k8s/secret.yaml
kubectl apply -f k8s/client-deployment.yaml
kubectl apply -f k8s/client-service.yaml   
kubectl apply -f k8s/server-deployment.yaml
kubectl apply -f k8s/server-service.yaml

kubectl get deployments
kubectl get services   
kubectl get pods

kubectl cluster-info
```

## To run Locally
Build Docker Image: With the Dockerfile ready, we can build a Docker image for our application.
```
docker build -t my-node-app .
```
Run Docker Container: Once the image is built, we can run a Docker container from it.
```
docker run -d -p 3000:3000 my-node-app
```
This command will start a container based on our image, and the Node.js application will be running inside the container, accessible at http://localhost:3000.

Automate Deployment: We can further automate the deployment process using Docker Compose or container orchestration tools like Kubernetes or Docker Swarm. These tools allow us to define the desired state of our application, including the number of replicas, resource constraints, networking configurations, etc., and automate the deployment and scaling process.

For example, with Docker Compose, we can define a docker-compose.yml file:
```
version: '3'
services:
my-node-app:
image: my-node-app
ports:
- "3000:3000"
```
And then deploy our application with a single command:
```
docker-compose up -d
```
This will start our application in a container, just like before, but now it's managed by Docker Compose.

By using Docker, we've simplified the deployment process by packaging our application and its dependencies into a single, portable container, making it easier to deploy consistently across different environments. Additionally, Docker allows us to automate the deployment process, reducing the likelihood of errors and speeding up the deployment cycle.






