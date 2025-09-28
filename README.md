# taskapi-kubernetes-fullstack
The Java REST API was containerized and deployed on Kubernetes with MongoDB (using persistent storage). Application and database run in separate pods, exposed via a Service. The TaskExecution endpoint was modified to create a temporary BusyBox pod through the Kubernetes API to run commands dynamically.
