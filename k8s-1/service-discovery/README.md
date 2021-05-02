kubectl create -f deployment-alpaca-prod.yaml
kubectl expose deployment alpaca-prod


kubectl get services -o wide

== NodePort

kubectl edit service alpaca-prod

""Change the spec.type field to NodePort.

kubectl get services -o wide

in browser <>:<port of NodePort service>

== LoadBalancer

kubectl edit service alpaca-prod

""Change the spec.type field to LoadBalancer.

