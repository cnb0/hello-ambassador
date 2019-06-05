# hello-ambassador

https://www.getambassador.io/user-guide/getting-started

Running ambassador in default namespace, when not installing Ambassador into the default namespace you must update the namespace used in the ClusterRoleBinding when RBAC is enabled.

```yaml
---
apiVersion: rbac.authorization.k8s.io/v1beta1
kind: ClusterRoleBinding
metadata:
  name: ambassador
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: ambassador
subjects:
- kind: ServiceAccount
  name: ambassador
  namespace: auth   #change this namespace
```
