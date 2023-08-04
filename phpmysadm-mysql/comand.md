## Create the deployment:  
kubectl apply -f mysql-deployment.yaml


php myadmin 

kubectl apply -f phpmyadmin-deployment.yaml


##  Access phpMyAdmin
minikube service phpmyadmin

```
Now, you should be able to access phpMyAdmin from your browser and connect to the MySQL database.

Please note, you'll want to make sure that the connection details like user name and password match 
your MySQL setup and are secured properly, especially in production environments!

```








## configMap

In the MySQL configuration provided in the ConfigMap, the lines under the [mysqld] section configure specific behavior for the MySQL server:

## skip-host-cache: 
This option disables the internal host cache that is used to improve performance by caching information about the client IP addresses. The host cache stores information about the clients, including errors encountered with clients, and can be used to limit the number of connections from any given client host. By skipping the host cache, you might experience a performance reduction in environments with a large number of connections, but it can be useful in scenarios where DNS is changing rapidly.

## skip-name-resolve: 
This option disables DNS hostname resolution. When this option is enabled, the MySQL server only uses IP addresses and not hostnames, meaning that all references to hostnames in commands like GRANT will not work. This can improve connection speed in environments where DNS resolution is slow or unreliable.

These options can be used to tune MySQL's performance and behavior in specific environments. Depending on your specific needs and network configuration, you might choose to include or exclude these options.



