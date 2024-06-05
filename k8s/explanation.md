# Orchestration (IP 4 explanation)

## Choice of Kubernetes Objects

### Client manifest
The client manifest file (client-deployment.yml) defines a **Deployment** object that manages the creation and maintenance of 3 Pods running the client application image (`mutevu/client:v1.0`). 

Since the application needs to be accessible externally, **LoadBalancer** type was used.

### Backend manifest

#### StatefulSet
The backend manifes file (backend-deployment.yml) defines as **StatefulSet** object. StatefulSets are preferred when it comes to managing stateful applications such as backend, which connects to a MongoDB database. 

Different from Deployments, the StatefulSets guarantee:

- Ordered Pod Creation: There is an order followed when it comes to creating and bringing online pods. This is important since the application relies on the stored dats.

- Persistent Identity: Each Pod in a StatefulSet has a unique and persistent hostname (determined by ordinal index within the set) that allows applications to establish connections and maintain state.

#### PersistentVolumeClaim

Even though it has not implicity defined in the manifest, the `volumeClaimTemplates` defines a template that will be used by Pods that will be created. 
