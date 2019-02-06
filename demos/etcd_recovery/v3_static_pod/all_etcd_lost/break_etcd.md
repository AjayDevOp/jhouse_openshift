Remove ETCD packages on all nodes to break etcd cluster
-------------------------------------------------------

To break all etcd perfectly, I choose package uninstallation.
This is the most critical situation. With this issue, OpenShift will be out of service.


## Remove all files under /var/lib/etcd on all ETCD nodes
```
mv /etc/origin/node/pods/etcd.yaml /etc/origin/node/pods-stopped/
rm -rf /var/lib/etcd/*
```

## Remove package on all ETCD nodes
```
yum remove etcd -y
```

## Check if oc is working
```
oc get pod
```

## [Next](./recover_first_etcd.md)
