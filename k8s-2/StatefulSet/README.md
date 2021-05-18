kubectl apply -f web.yaml
 kubectl get service nginx
 kubectl get statefulset
 kubectl get pod

For a StatefulSet with N replicas, when Pods are being deployed, they are created sequentially, in order from {0..N-1}. Examine the output of the kubectl get command in the first terminal. Eventually, the output will look like the example below.

Pods in a StatefulSet have a unique ordinal index and a stable network identity.
for i in 0 1; do kubectl exec web-$i -- sh -c 'hostname'; done
kubectl run -i --tty --image busybox:1.28 dns-test --restart=Never --rm  nslookup web-0.nginx
kubectl run -i --tty --image busybox:1.28 dns-test --restart=Never --rm  nslookup web-1.nginx

kubectl get pvc

kubectl scale sts web --replicas=5

--- 
kubectl delete sts web
kubectl delete sts web --cascade=false
