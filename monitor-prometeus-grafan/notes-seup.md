Step 1: Set Up Prometheus
1.1 Create a ConfigMap for Prometheus Configuration

Create a file called prometheus-config.yaml:


kubectl apply -f prometheus-config.yaml



1.2 Create a Deployment for Prometheus

Create a file called prometheus-deployment.yaml


kubectl apply -f prometheus-deployment.yaml



prometheus-service.yaml


kubectl apply -f prometheus-service.yaml




Step 2: Set Up Grafana
2.1 Create a Secret for Grafana Admin Password

Create a file called grafana-secret.yaml:

kubectl apply -f grafana-secret.yaml

2.2 Create a Deployment for Grafana

Create a file called grafana-deployment.yaml:


kubectl apply -f grafana-deployment.yaml



2.3 Create a Service for Grafana

Create a file called grafana-service.yaml

kubectl apply -f grafana-service.yaml


Step 3: Access Prometheus and Grafana

You can access Prometheus and Grafana through the NodePort services created earlier.

For Prometheus:


minikube service prometheus


for grafana:
minikube service grafana



#####
In Grafana, you can add Prometheus as a data source and start creating dashboards to visualize your Kubernetes metrics.

Make sure to replace placeholder values such as the Grafana admin password with appropriate values for your environment, and keep them secure!





















