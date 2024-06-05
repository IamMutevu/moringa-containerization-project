# Orchestration (IP 4 explanation)

## Prerequisites
- Ensure you have the Google Cloud SDK (gcloud) installed and configured on your local machine.
- Ensure the Kubernetes Engine API is enabled in the project you are using to proceed.  

## Deployment Steps 
### Create the cluster

From the cloud shell, run the following command to create a cluster. The command defines the name of the cluster, the zone and the number of nodes to run. 

`gcloud container clusters create yolo-project --region us-central1 --num-nodes 2`

### Authenticate with GKE Clusters

`gcloud container clusters get-credentials yolo-project --region us-central1`

### Create Namespaces

```
kubectl create namespace backend
kubectl create namespace client
```
### Apply Deployment Manifests

Apply the deployment manifests to deploy the backend and client applications:

```
kubectl apply -f backend-deployment.yaml -n backend
kubectl apply -f client-deployment.yaml -n client
```

### Apply Service Manifests

Apply the service manifests to expose the applications

```
kubectl apply -f backend-service.yaml -n backend
kubectl apply -f client-service.yaml -n client
```

## Verify Deployment

### Check Deplyment Status

Replace <namespace> with the namespace you want to check status for. The command should show the deplyments in a "running" state with the desired number of replicas.

```
kubectl get deployments -n <namespace> 
```

### Check Pod Status

```
kubectl get pods -n <namespace> 
```