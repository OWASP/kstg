# Discovery

The *discovery* section cover various techniques and procedures for discovering various components of a Kubernetes cluster. This primarily involves

1. Ability to discover master node(s)
2. Ability to discover worker node(s)

## Network Discovery

Common ports for master node discovery

| Port            | Protocol | Service                                                         |
| :-------------- | :------- | :-------------------------------------------------------------- |
| 443, 6443, 8443 | TCP      | Kubernetes API Server (`kube-apiserver`)                        |
| 8080            | TCP      | Kubernetes API Server insecure port (Listens on localhost only) |
| 2379, 2380      | TCP      | etcd server                                                     |

Common ports for worker node discovery

| Port        | Protocol | Service                               |
| :---------- | :------- | :------------------------------------ |
| 10250       | TCP      | Kubelet                               |
| 10255       | TCP      | Kubelet read-only port                |
| 30000-32767 | TCP      | nodePort service port range (default) |

Given the above network services information, Kubernetes master or worker nodes can be discovered by scanning a network CIDR for ports, for example:

To discover master nodes

```bash
nmap -Pn -sS -sV -p 443,6443,8443,8080,2379,2380 $CIDR
```

To discover worker nodes

```bash
nmap -Pn -sS -sV -p 10250,10255 $CIDR
```

To discover `nodePort` exposed services

```bash
nmap -Pn -sS -sV -p 30000-32767 $CIDR
```
