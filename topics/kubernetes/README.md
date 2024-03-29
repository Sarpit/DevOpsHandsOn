# Kubernetes Resources

## Namespaces

<details>
<summary>What Namespace is?</summary></br><b>
In Kubernetes, a namespace is a way to create multiple virtual clusters within the same physical cluster. It is a logical partitioning mechanism that allows you to organize and isolate resources within the cluster. Each namespace provides its own scope for resources, and it's like a virtual cluster within the larger Kubernetes cluster.</br></b>
By default, a <b>default</b> namespace is already selected in a cluster to provision workloads.
</details>

<details>
<summary>Why do we need different namespaces for different applications?</summary></br>
<b>Resource Isolation:</b> Namespaces provide a way to isolate resources between different applications or environments.</br>
<b>Access Control:</b> Namespaces enable access control by allowing you to define RBAC (Role-Based Access Control) policies specific to each namespace. This means you can control who can view or modify resources within a particular namespace without affecting resources in other namespaces.</br>
<b>Resource Quotas and Limits:</b> Namespaces allow you to set resource quotas and limits at the namespace level. This helps in preventing a single application or team from consuming all available resources in the cluster.</br>
<b>Easier Monitoring and Troubleshooting:</b> With namespaces, you can monitor and troubleshoot applications more efficiently.</br>
</details>

<details>
<summary>How to create kubernetes namespace?</summary><br><b>

`kubectl create namespace dev`
</b></details>

<details>
<summary>How many namespaces are created by default?</summary></br>
There are 4 namespaces that are created by default</br></br>
<b>kube-system</b>: kubernetes component are deployed in this namespace such as ApiServer, ETCD, Scheduler</br>
<b>kube-public</b>: Publicly accessible data is stored in this namespace</br>
<b>kube-node-lease</b>: This namespace holds Lease objects associated with each node. Node leases allow the kubelet to send heartbeats so that the control plane can detect node failure.</br>
<b>default</b>: workload are created here by default ( if no namespaced is defined )</br>
</details>


# Kubernetes Exercise

|Name|Topic|Objective & Instructions|Solution|Comments|
|--------|--------|------|----|----|
| Creating Pod | Pods | [Exercise](pod_01.md) | | |
| Resource Request | Pods | [Exercise](pod_02.md) | | |
| Command and Arguments | Pods | [Exercise](pod_03.md) | | |
| Static Pods | Pods | [Exercise](pod_04.md) | | |
| Troubleshooting errors | Pods | [Exercise](pod_05.md) | | |
