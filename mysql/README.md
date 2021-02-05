Example of Kubernetes with mysql from url below

https://kubernetes.io/docs/tasks/run-application/run-single-instance-stateful-application/


```
ip=$(kubectl get svc | grep "^mysql " | awk '{print $3}')
mysql -ppassword -h $ip 
```
