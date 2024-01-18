# Pods 05

#### Objective 

Troubleshooting errors

#### Instruction

1. Fix the following Pod definition file.
```yaml
apiVersion: apps/v1
kind: pod
metadata:
  labels:
    app: nginx
  name: nginx
spec:
  containers:
  - image: nginx
    name: nginx:2.7
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: always
status: {}
```

2. After fixing, run the pod with <code>kubectl apply</code>
