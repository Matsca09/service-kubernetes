Automium Service: kubernetes 
======================================

[![pipeline status](https://gitlab.com/automium/service-kubernetes/badges/master/pipeline.svg)](https://gitlab.com/automium/service-kubernetes/commits/master)

this project is meant to be used by [automium provisioner](https://github.com/automium/provisioner)

## variables

### MASTER

if true configure the instance as a kubernetes master node

### NODE

if true configure the instance as a kubernetes worker node

### ETCD

if true configure the instance as a etcd node

### KUBE_CONF _optional_

[kubespray variables](https://github.com/kubernetes-sigs/kubespray/blob/master/docs/vars.md)

es. in docker compose:
```
environment:
  KUBE_CONF: |-
    podsecuritypolicy_enabled: true
    kubelet_custom_flags:
      - "--event-qps=0"
```

### RANCHER_URL _optional_

rancher http url

### RANCHER_CLUSTER_TOKEN _optional_

rancher token

### AUTOMIUM_AUTOSCALER_KUBECONFIG _optional_

base64 automium kubeconfig

### LOG_FILEBEAT_ES_URL _optional_ 

elasticsearch URL for filebeat logs

### LOG_FILEBEAT_ES_URL_PATH _optional_

path on which elasticsearch is exposed on the provided URL

### LOG_FILEBEAT_ES_USER _optional_

basic auth username for elasticsearch 

### LOG_FILEBEAT_ES_PASS _optional_ 

basic auth password for elasticsearch 

## usage

setup service var:
```
export SERVICE=automium/service-kubernetes
export MASTER=true
export NODE=true
export ETCD=true
export RANCHER_URL=http://rancher.local
export RANCHER_CLUSTER_TOKEN=237dh928gd2
export AUTOMIUM_AUTOSCALER_KUBECONFIG=YPBpVmVyq2lvbjogdjEKY2x1c3...RlWTFVMjU2Vkc1Q2RYTjZVMGhpYm1wUfo=
export LOG_FILEBEAT_ES_URL=http://es.local:80
export LOG_FILEBEAT_ES_URL_PATH=/es
export LOG_FILEBEAT_ES_USER=myusername
export LOG_FILEBEAT_ES_PASS=mypass
```

and follow the guide [here](https://github.com/automium/provisioner/blob/master/README.md#guide)
