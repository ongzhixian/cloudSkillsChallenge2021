# Kubernetes

Hosting microservices inside of a container is a common way to achieve that. 
These kinds of systems are complex to scale out and manage. 
You need to consider the process of organizing, adding, removing, and updating many containers. 
This process is referred to as container management.

To help with container management tasks, you can use a container orchestrator. 
Kubernetes is one such orchestrator. 
It is an extensible open-source platform for managing and orchestrating containerized workloads.

## tldr;

Kubernetes, container orchestrator to help with container management tasks.

## Container management tasks

These tasks include:

    Self-healing of containers. An example would be restarting containers that fail or replacing containers.
    Scaling deployed container count up or down dynamically, based on demand.
    Automating rolling updates and rollbacks of containers.
    Managing storage.
    Managing network traffic.
    Storing and managing sensitive information, such as usernames and passwords.

Because Kuberentes is a tool to orchestrate containerized workloads, 
and you can deploy .NET microservices into containers, you can use Kubernetes to orchestrate your .NET microservices. 
