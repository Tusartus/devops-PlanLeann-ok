



kubectl apply -f mysql-configmap.yaml


step 3:   Deploy MySQL



kubectl apply -f mysql-deployment.yaml



# Step 4: Deploy WordPress

kubectl apply -f wordpress-deployment.yaml



5: 

## step 5: Expose WordPress

To access WordPress from your browser, expose it:
##
kubectl expose deployment wordpress --type=NodePort --port=80


## Step 6: Access WordPress

Use Minikube to find the URL to access WordPress in your browser:

minikube service wordpress



