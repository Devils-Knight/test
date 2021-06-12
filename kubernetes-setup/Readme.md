# Kubernetes-Setup
****
Instructions to setup a multi node Kubernetes cluster for development purposes
## Prerequisites
***
- Vagrant should be installed on your machine. Installation binaries can be found here.
- Oracle VirtualBox can be used as a Vagrant provider or make use of similar providers as described in Vagrant's official documentation.
- Ansible should be installed in your machine. Refer to the Ansible installation guide for platform specific installation.


## Running this Playbook
***
Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/Devils-Knight/test
```

### 2. Execute Vagrantfile

```shell
cd test/kubernetes-setup
$ vagrant up
```

### 3. Accessing master and nodes

```shell
$ ## Accessing master
$ vagrant ssh k8s-master
vagrant@k8s-master:~$ kubectl get nodes
NAME         STATUS   ROLES    AGE     VERSION
k8s-master   Ready    master   18m     v1.13.3
node-1       Ready    <none>   12m     v1.13.3
node-2       Ready    <none>   6m22s   v1.13.3

$ ## Accessing nodes
$ vagrant ssh node-1
$ vagrant ssh node-2
```