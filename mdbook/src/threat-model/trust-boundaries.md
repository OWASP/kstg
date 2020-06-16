# Trust Boundaries

*Trust Boundary* or *Zone* segregates different components in a *Data Flow Diagram* based on sensitivity and level of access to critical assets in the system. The [Kubernetes Threat Model](https://github.com/kubernetes/community/raw/master/wg-security-audit/findings/Kubernetes%20Threat%20Model.pdf) by [Security Audit Working Group](https://github.com/kubernetes/community/raw/master/wg-security-audit/) defines the following trust boundaries which we will refer in the testing methodology

| Zone              | Description                                                                                          |
| ----------------- | ---------------------------------------------------------------------------------------------------- |
| Internet          | The externally facing, wider internet zone                                                           |
| API Server        | The master component, usually exposed to cluster users, needed for interaction with `kubectl`        |
| Master Components | Internal components of the master node that works via. callbacks and subscriptions to the API Server |
| Master Data       | The master data layer that stores the cluster state. Example: `etcd`                                 |
| Worker            | The worker components that is required to add a node in the cluster and to run containers            |
| Container         | The containers being orchestrated by the cluster                                                     |
