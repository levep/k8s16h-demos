Create Namespace + runnig pod + set context + delete namespace, intro to kubectl commandline
================================================

    $ kubectl create -f namespaces-dev.json

    $ kubectl get namespace

    $ kubectl run  kuard --image=gcr.io/kuar-demo/kuard-amd64:1 -n development
    $ kubectl port-forward  --address 0.0.0.0 kuard  8080:8080
    $ kubectl get pods -n development

#kubectl conventions: https://kubernetes.io/docs/reference/kubectl/conventions/
-------------------

    $  kubectl config set-context --current --namespace=development

    $ kubectl get pods kuard -o yaml

    $ kubectl get pods kuard -o json

    $ kubectl edit pods kuard

#kubectl context and configuration: https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#config
---------------------------------

    $ kubectl config set-context --current --namespace=default

    $ kubectl delete namespace development


------
One pattern this organization could follow is to partition the Kubernetes cluster into two namespaces: development and production.
Let's create two new namespaces to hold our work. Create the development and production namespaces using kubectl:

    $ kubectl create -f namespace-dev.yaml
    $ kubectl create -f namespace-prod.yaml

kubectl create deployment snowflake --image=k8s.gcr.io/serve_hostname  -n=development --replicas=2

kubectl create deployment cattle --image=k8s.gcr.io/serve_hostname -n=production
kubectl scale deployment cattle --replicas=5 -n=production

-----
https://kubernetes.io/docs/tasks/administer-cluster/namespaces/#creating-a-new-namespace