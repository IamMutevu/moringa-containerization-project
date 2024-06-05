# Orchestration (IP 4 explanation)

## Choice of Kubernetes Objects

The client manifest file defines a **Deployment object** that manages the creation and maintenance of 3 Pods running the client application image (`mutevu/client:v1.0`). 

Since the application needs to be accessible externally, **LoadBalancer** type was used.


