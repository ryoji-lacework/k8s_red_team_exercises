Kubernetes Red Team Exercises
This repository contains a collection of Kubernetes deployment YAML files designed for security training and red team exercises. Each deployment showcases different security configurations and scenarios, ranging from privilege escalation to deploying vulnerable applications like JuiceShop. The goal is to provide a hands-on learning experience for understanding Kubernetes security mechanisms, potential misconfigurations, and their implications.

Getting Started
Before you begin, ensure you have the following prerequisites installed and configured:

kubectl: The Kubernetes command-line tool, which allows you to run commands against Kubernetes clusters.
A Kubernetes cluster: You can use Minikube for a local setup, or a cloud provider's Kubernetes service for a more realistic environment.
Usage
To use the YAML files in this repository, first clone the repo to your local machine:

bash
Copy code
git clone https://github.com/ryoji-lacework/k8s_red_team_exercises.git
cd k8s_red_team_exercises
Then, apply the desired YAML file to your Kubernetes cluster using kubectl:

bash
Copy code
kubectl apply -f <filename>.yaml
Replace <filename> with the name of the YAML file you wish to deploy.

Exercises Overview
The repository is structured with individual YAML files, each representing a specific security scenario:

1. Privileged Container Deployment
File: privileged-deployment.yaml
Purpose: Demonstrates the creation of a container with elevated privileges (privileged: true) and allows privilege escalation within the container. This can be used to understand the risks associated with running containers in privileged mode.
2. Allow Privilege Escalation
File: allow-privilege-escalation.yaml
Purpose: Showcases a deployment where a container is configured to allow privilege escalation (allowPrivilegeEscalation: true). Useful for understanding how containers can gain additional privileges and the potential security implications.
3. Deploying JuiceShop
File: juiceshop-deployment.yaml
Purpose: Deploys the OWASP JuiceShop, a purposely vulnerable web application, within a Kubernetes cluster. This exercise is aimed at exploring common web application vulnerabilities in a containerized environment.
Detecting and Mitigating Risks
After deploying each scenario, you can explore various methods to detect and mitigate the potential risks associated with the configurations. This may include configuring network policies, applying Pod Security Policies (PSPs), or using security tools designed for Kubernetes environments.

Cleanup
To remove a deployed exercise from your cluster, use the delete command:

bash
Copy code
kubectl delete -f <filename>.yaml

Disclaimer
These exercises are intended for educational purposes only. Do not deploy these configurations in production or other sensitive environments without proper security controls in place.
