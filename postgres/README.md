Simple example of postgres on kubernetes with statefulsets

From kubernetes do

Start
```
./apply
./test
```

delete resources
```
./delete
```

Other methods of interacting
```
ip=$(kubectl get svc | grep "^postgres-service " | awk '{print $3}')

apt install postgres-client
psql -h 10.152.183.170 -U demouser -d demodb 

sudo microk8s.kubectl run psql -it --rm=true --image=postgres:12 --command -- psql -h $ip -U demouser demodb
```

Directing traffic to Kubernetes cluster

routing
```
sudo ip route add 10.152.183.170(nodeport) via 10.x.x.x(kubegateway)
```

dnat
```
```

```
kubectl exec --stdin --tty postgres-5c64546cbf-tmrgl -- /bin/bash
```

Tear down and build up
```
./delete && ./apply
```
