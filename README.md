# kubeadm-cluster

kubeadmin-cluster is a k8s cluster on vagrant for local developing and testing. 

## How to use

This repository has 4 directories. Each directory is correspond to one k8s node and has vargrant file of master and workers  

First install vagrant 2.0.0 or up

Clone this repository

    $ git clone https://github.com/itchain/kubeadm-cluster.git

Go to “master” directory and run vagrant

    $ cd master
    $ vargrant up

After master vm was created, run `vargrant up` command in each worker directory(worker1, 2, 3)

    $ cd worker1
    $ vagrant up

And then the worker node(vm) was joined to master node. To verify all worker node are joined crrectly, login with ssh to master and run follows commands

    $ cd master
    $ vagrant ssh
    $ master> sudo su
    $ master> kubectl get node

If all node status are “Ready”, the k8s cluster is configured rightly.

To destory cluster, run `vagrant destroy` in each directories.

    $ cd master
    $ vagrant destroy
    $ cd worker1
    $ vagrant destroy
    ...

