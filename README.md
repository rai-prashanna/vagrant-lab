# Ubuntu 17.10 cluster via Vagrant

This repository provides a template Vagrantfile to create a Ubuntu 17.10 cluster using the VirtualBox software hypervisor.
After setup is complete you will have three CentOS virtual machines running on your local machine.   

Please be aware that the standard memory per instance is set to 3072 MB, and the cpu cores to 2. That means by default you'll need a machine capable to free up to 6 cpu cores and 9216 MB memory.  

## Streamlined setup

### Install dependencies

* [VirtualBox][virtualbox] 4.3.10 or greater.
* [Vagrant][vagrant] 1.6 or greater.

### Clone this project and get it running!

```
git clone 
cd vagrant-cluster-centos
```

### Startup and SSH

The VirtualBox provider is the default Vagrant provider. Use this if you are unsure.

```
vagrant up
vagrant ssh prai-01
```




#01==08:00:27:31:b9:6a;;;4A1B6C3B-96E1-4056-B7B9-B26BB2709D4A;;172.17.11.101 
#02==08:00:27:49:ec:24;;;5C6F3273-9D9B-4984-822C-187CDC5042F7
#03==08:00:27:f2:41:e4;;;;C34B0E4C-0486-414E-B3A3-10506E92AF3F

sudo kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-advertise-address=172.18.0.1 ​
sudo kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-advertise-address=172.17.11.101

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

You can now join any number of machines by running the following on each node
as root:

  kubeadm join 172.17.11.101:6443 --token n5nt0m.95bg26s5lx50iout --discovery-token-ca-cert-hash sha256:3e9629364e4e973911a61aafa7451b522cedb3bb041e4e088aeb862ca1e4af3d
  
##kubectl get pods --all-namespaces
##kubectl get nodes
##kubectl run nginx --image=nginx
## kubectl get pods
  













