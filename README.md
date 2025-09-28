Task Management System – Kubernetes Busybox
Overview
This project implements a Task Management System using Kubernetes and Busybox pods. Users can create command-based tasks that execute in isolated Busybox pods. The UI allows managing, running, and monitoring tasks, while backend APIs support automation and integration.

Prerequisites
-Kubernetes cluster (minikube, Docker Desktop, or cloud provider)
-kubectl CLI installed/configured
-Docker (for building/deploying images)
-MongoDB running (as a pod/service)
-PowerShell recommended for API testing on Windows

Setup Instructions
-Clone the Repository
  Download or clone the project files to your local machine.
-Deploy Backend and Database
  Deploy mongodb as a Kubernetes deployment and service.
  Deploy Java/Spring Boot backend and task-api components as deployments/services.-
-Start Frontend
  Launch the frontend at http://localhost:3000.
-Verify Deployments
  Make sure all pods, services, and deployments are running using:
kubectl get all

Usage Instructions
-Create a Task
  Use the web interface to create new tasks. Define a name, owner, and command (e.g., echo "Hello World").
-Execute a Task
  Launch execution using the "Execute" button on the web UI – a Busybox pod will run the specified command.
-Monitor and Manage Tasks
  View history, executions, and command output through the web interface.
  Refresh the web page or run kubectl commands to check execution status.
-Delete Tasks/Pods
  Use the "Delete" button in the UI or cleanup old pods using CLI (see Commands section).

Main Commands
kubectl get pods | findstr task-exec
kubectl logs <task-exec-pod>
kubectl delete pod <pod-name>
kubectl get pods -w
kubectl get all
kubectl get services
kubectl get pods

PowerShell API Testing:
Invoke-WebRequest -uri http://localhost:3000/tasks
Invoke-WebRequest Uri http://localhost:3000/tasks

Access the Web App:
http://localhost:3000

REST API Endpoints
List Tasks:
GET http://localhost:3000/tasks
Returns a JSON listing of all tasks and their execution history.

Architectural Components
Pods:
mongodb
myapp (Java/Spring Boot backend)
task-exec-* (Busybox for command execution)
taskapi

Services:

mongodb
myapp
taskapi

Frontend:
localhost:3000

Troubleshooting
Check all resources:
kubectl get all

Check pod and service status:
kubectl get pods
kubectl get services

Delete stuck/old pods:
kubectl delete pod <pod-name>

Conclusion
This system provides a modular approach to running, tracking, and managing shell command tasks in Kubernetes using Busybox pods. It combines a friendly web interface with robust command-line and REST API access for automation and scripting.
