### kubectl apply commands in order
    
    kubectl apply -f mongo-secret.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-configmap.yaml 
    kubectl apply -f mongo-express.yaml

### kubectl get commands

    kubectl get pod
    kubectl get pod --watch
    kubectl get pod -o wide
    kubectl get service
    kubectl get secret
    kubectl get all | grep mongodb

### kubectl debugging commands

    kubectl describe pod mongodb-deployment-xxxxxx
    kubectl describe service mongodb-service
    kubectl logs mongo-express-xxxxxx

### give a URL to external service in minikube

    minikube service mongo-express-service




## in mongo -secret 

- echo -n mongouser | base64

- echo -n mongopassword | base64



## bron:
- https://www.youtube.com/watch?v=X48VuDVv0do&t=4768s

- 

## access mongoexpress service loadbalancer on brouwser

- kubectl get service

- minikube service mongo-express-service   ###  to open in brouwser.


### see mongo 

 kubectl get service
 kubectl describe service mongodb-service   ## port listing to : entrypoint 











## bron: node expess app:webapp from docker userhub +  mongo, config SECRET.
 https://www.youtube.com/watch?v=s_o8dwzRlu4&t=3816s

 https://gitlab.com/nanuchi/k8s-in-1-hour


kubectl get pod | configmap | secret | ...

kubectl describe service  nameofservice


--------------------------------------------------------------------------------------------------------------



access in brouwser : kubectl get svc      NodePort or loadbanler type : kan be in browser with port 
- minikube ip 

or 
kubectl get node

kubectl get node -o wide

to access webappservice 

















