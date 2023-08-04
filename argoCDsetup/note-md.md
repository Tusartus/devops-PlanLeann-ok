Setting up Argo CD in Kubernetes without Helm can be done using YAML manifests and the kubectl command. Here are the steps:
Step 1: Create the Argo CD Namespace

First, create a namespace for Argo CD. Save this YAML as argo-namespace.yaml:


apiVersion: v1
kind: Namespace
metadata:
  name: argocd


apply it:
kubectl apply -f argo-namespace.yaml


Step 2: Deploy Argo CD

Argo CD provides an official YAML file to deploy Argo CD into a Kubernetes cluster. You can apply it directly from their GitHub repository:


kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.1.1/manifests/install.yaml



Make sure to use the URL corresponding to the version of Argo CD you want to install.
Step 3: Expose the Argo CD API Server

By default, the Argo CD API server is not exposed externally. You can expose it using a NodePort or LoadBalancer service. For example, you can edit the existing service to use a NodePort:


kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'



Step 5: Access the Argo CD Web UI

If you've exposed the Argo CD API server using a NodePort (as in step 3), you can find the URL with:

minikube service argocd-server -n argocd


###
Then, log in with the username admin and the password you retrieved in step 4.
Step 6: Change the Default Password (Optional but Recommended)

You can change the default password using the Argo CD CLI or through the web UI after you log in. For CLI, you'll need to install the Argo CD CLI tool and use the argocd command.

These steps will set up Argo CD in a default configuration, and you can further customize it based on your specific requirements and environment. Make sure to consult the official Argo CD documentation: https://argo-cd.readthedocs.io/en/stable/ for more details and best practices.












