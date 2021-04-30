# Helm

```
 $ microk8s.helm3 repo add stable https://kubernetes-charts.storage.googleapis.com/

$ microk8s.helm3 search repo stable

$ cd /tmp; microk8s.helm3 fetch stable/tomcat

$ tar xfvz tomcat-0.4.1.tgz; cd tomcat
```

```
$ microk8s.helm3 install my-release stable/tomcat

$  kubectl get svc --namespace default my-release-tomcat
```