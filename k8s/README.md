# Orchestration (IP 4 explanation)

## Enable API

Ensure the Kubernetes Engine API is enabled to proceed.  

## Create the cluster

From the cloud shell, run the following command to create a cluster. The command defines the name of the cluster, the zone and the number of nodes to run. 

`gcloud container clusters create yolo-project --zone=asia-south1 --num-nodes=2`