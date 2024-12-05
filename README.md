# cosmocloud-deploy

# **Cosmocloud-Deploy Helm Chart:**

This repository contains the Helm chart cosmocloud-deploy for deploying a complete application stack consisting of a Frontend, Backend, and Redis Database using Kubernetes. This chart simplifies the deployment and management of these components in a Kubernetes cluster.

______

# **Introduction:**

The goal of this project is to deploy three services:
- Backend
- Frontend
- Redis 

______

# **Prerequisites:**

- Kubernetes cluster.
- Helm installed on your machine.
- Basic knowledge of Kubernetes concepts like Pods, Deployments, and Services.

________

# **File Information:**

- templates/: Kubernetes manifests for deploying the application.
- Chart.yaml: Metadata about the Helm chart.
- values.yaml: Configuration values for the Helm chart.

__________

# **How to Use:**

- Deploy the application:
helm install testapp cosmocloud-deploy --atomic --timeout 30s

- Verify the deployment:
kubectl get svc
kubectl get pods

______________

# **Details:**

Components:

- Backend
Image: shreybatra/sample-backend
Environment Variable: REDIS_URI=redis://redis-svc:6379
Service: backend-svc, ClusterIP, Port 8000.

- Frontend
Image: shreybatra/sample-frontend
Environment Variable: BACKEND_URL=http://backend-svc:8000
Service: frontend-svc, NodePort, Port 5175, NodePort 31000.

- Redis
Image: redis
Service: redis-svc, ClusterIP, Port 6379.

______________





