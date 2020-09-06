# Docker-Swarm-Setup

### For centOS7 && Docker version 19.03.12

## 1. set up hosts static IP

```
sudo vim /etc/hosts
```

```
192.168.89.102  managernode
192.168.89.103  workernode1
192.168.89.104  workernode2
```

## 2. Set up IP address

### Manager node:

```
sudo hostnamectl set-hostname managernode
```

### Worker node1:

```
sudo hostnamectl set-hostname workernode1
```

### Worker node2

```
sudo hostnamectl set-hostname workernode2
```

## 3. Fire wall

```
sudo firewall-cmd --permanent --add-port=2376/tcp
sudo firewall-cmd --permanent --add-port=2377/tcp
sudo firewall-cmd --permanent --add-port=7946/tcp
sudo firewall-cmd --permanent --add-port=80/tcp
sudo firewall-cmd --permanent --add-port=7946/udp
sudo firewall-cmd --permanent --add-port=4789/udp
```

## 4. Reload Docker and firewall 

```
sudo firewall-cmd --reload
sudo systemctl restart docker
```

## 5. Config cluster

Manager node

```
sudo docker swarm init --force-new-cluster
```

Worker node

Docker swarm uses port 2377 by default.

```
sudo swarm join --token <token> <MANAGER_IP_ADDRESS>:2377
```
