# kubeadm Ansible Playbook for Centos 7

This is a simple playbook to wrap the following operations:

* Install the kubeadm repo
* Install docker, kubeadm, kubelet, kubernetes-cni, and kubectl
* Disable SELinux :disappointed:
* Set docker `--logging-driver=json-file`
* Set docker `--storage-driver=overlay`
* Set kubelet `--cgroup-driver=systemd`
* Optional: Configure an insecure registry for docker
* Initialize the cluster on master with `kubeadm init`
* Install user specified pod network from `group_vars/all`
* Join the nodes to the cluster with 'kubeadm join`

This has been tested with **CentOS 7.3** and **Kubernetes v1.6.1**

At the end of the playbook, either copy `/etc/kubernetes/admin.conf` to `$HOME/config` or `export KUBECONFIG=/etc/kubernetes/admin.conf` and `kubectl` will operate on the new cluster.
