```
[vs]~/Downloads/ops-task-master/kube [master] $ kubectl get pods --namespace ops-demo
NAME                           READY   STATUS    RESTARTS   AGE
ops-demo-app-67bdcbbff-b724b   1/1     Running   1          2m38s
ops-demo-app-67bdcbbff-x44nr   1/1     Running   0          2m41s
redis-85b59c5489-bpzjp         1/1     Running   0          2m35s
[vs]~/Downloads/ops-task-master/kube [master] $ kubectl get deployments --namespace ops-demo
NAME           READY   UP-TO-DATE   AVAILABLE   AGE
ops-demo-app   2/2     2            2           17m
redis          1/1     1            1           17m
[vs]~/Downloads/ops-task-master/kube [master] $ kubectl get services --namespace ops-demo
NAME           TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
ops-demo-app   LoadBalancer   10.105.182.44    <pending>     3000:31341/TCP   17m
redis          ClusterIP      10.109.248.227   <none>        6379/TCP         17m

[vs]~/Downloads/ops-task-master [master] $ minikube service ops-demo-app --namespace ops-demo
|-----------|--------------|-------------|-----------------------------|
| NAMESPACE |     NAME     | TARGET PORT |             URL             |
|-----------|--------------|-------------|-----------------------------|
| ops-demo  | ops-demo-app |             | http://192.168.99.102:31341 |
|-----------|--------------|-------------|-----------------------------|



[vs]~/Downloads/ops-task-master/kube [master] $ curl http://192.168.99.102:31341
welcome to api 4[vs]~/Downloads/ops-task-master/kube [master] $ curl http://192.168.99.102:31341
welcome to api 5[vs]~/Downloads/ops-task-master/kube [master] $ curl http://192.168.99.102:31341
welcome to api 6
```
