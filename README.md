# Kubernetes Installation
## Master and worker
### Run the following commands :

```bash
 sudo apt update
```

```bash
 sudo apt upgrade -y
```

### Configure the hostname
Keep the hostname as master for master node and worker for worker node
```bash
 nano /etc/hostname
```

### Update the etc/hosts file:
```bash
 nano /etc/hosts
```
The etc/hosts should look like this
```
something its_ip
master master_ip
worker worker_ip
```

### Reboot the system
```bash
reboot
```

## Master
On the master node , create a script and run the **master.sh** script.
```bash
nano master.sh
./master.sh
```
On executing *./master.sh* if CLI shows permission denied, then run
```bash
chmod +x master.sh
./master.sh
```

## Worker
On the worker node , create a script and run the **worker.sh** script.
```bash
nano worker.sh
./worker.sh
```

 If on master or worker node,  error of unable to locate package kubeadm ,kubelet , kubectl , kubernetes-cni is there, then run the **xenial_error.sh** script on master and worker nodes. Now, run the **master.sh** in master node and **worker.sh** in worker node again.
 
***
 #### The master node will generate a key as kubeadm join '-------' copy that key and run it on the worker nodes.
***

## Master
On the master , run the following command
```bash
kubectl get nodes
```
It will show the nodes and in what state(ready/not ready) the nodes are.

Run this command to see the pods
```bash
kubectl get pods -A
```


 

 





