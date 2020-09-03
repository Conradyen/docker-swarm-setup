# Start service on manager node

```
docker service create -p 80:80 --name <NAME> --replicas 3 <IMAGE>
```

# Stop service on cluster

```
sudo docker service rm <SERVICE_NAME>
```
