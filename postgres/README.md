Simple example of postgres on kubernetes with statefulsets

From kubernetes do

Start
```
./up
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
psql -h 10.152.183.170 -U amazinguser -d awesomedb

sudo microk8s.kubectl run psql -it --rm=true --image=postgres:12 --command -- psql -h $ip -U amazinguser awesomedb
```
