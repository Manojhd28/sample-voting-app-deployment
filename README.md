**Voting App Deployment on Kubernetes**

A microservices-based Voting Application deployed on Kubernetes to demonstrate scalability, container orchestration, and efficient service management.

**1. Project Overview**
   
This project implements a Voting Application where users can cast votes and view results in real-time. It highlights skills in deploying and managing containerized microservices using Kubernetes, with Redis for caching, PostgreSQL for database management, and Docker for containerization.

**2. Architecture**

The application follows a microservices architecture and includes five main components:

![image](https://github.com/user-attachments/assets/fbae9783-0c4a-4905-973c-94aa282b2321)

**3. Technologies Used**

Kubernetes: Orchestrates the deployment of containerized services.

Docker: Packages the application services.

Redis: Used for caching votes.

PostgreSQL: Stores voting data.

Helm (optional): Manages application configurations if desired.

**4. Setup & Installation**

To deploy this project, ensure the following prerequisites:

Kubernetes Cluster: A running Kubernetes cluster (local or cloud-based).

kubectl: Installed for command-line interaction with Kubernetes.

Docker: For building and managing container images.

clone this repository

git clone https://github.com/seemab28/sample-voting-app-deployment.git

cd sample-voting-app-deployment

**5. Deployment**

To deploy the Voting Application, apply each Kubernetes configuration file in the following order.

Create Deployments and Services: Use the kubectl apply command to deploy each component:

kubectl apply -f db-deployment.yaml

kubectl apply -f db-service.yaml

kubectl apply -f redis-deployment.yaml

kubectl apply -f redis-service.yaml

kubectl apply -f vote-deployment.yaml

kubectl apply -f vote-service.yaml

kubectl apply -f worker_deployment.yaml

kubectl apply -f result-deployment.yaml

kubectl apply -f result-service.yaml

Verify Pods and Services:

kubectl get pods

kubectl get svc

Access Application: Expose ports as defined in the service files (e.g., vote-service.yaml and result-service.yaml) to access the application.

**6. Scaling & Upgrading**
   
Scale Services: Adjust the number of replicas for higher availability.

kubectl scale deployment vote --replicas=3

kubectl scale deployment result --replicas=3

Upgrade Microservices: Update the image version in YAML files (e.g., kodekloud/examplevotingapp_vote:after for the voting service), then reapply configurations:

kubectl apply -f vote-deployment.yaml

**7. Debugging**
   
If the application is not functioning as expected:

Check the status of each service:

kubectl get pods -o wide

kubectl logs <pod-name>

Use kubectl describe to see detailed Pod/Service configurations.

**8. Usage**
   
Access the Voting App on the defined port (e.g., 31000) to submit votes.

Access the Result App on its port (e.g., 31001) to view real-time voting results.

**10. Contributing**

Contributions are welcome! Please fork the repository and submit a pull request.




