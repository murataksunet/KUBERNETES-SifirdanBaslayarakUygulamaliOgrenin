## 🧑 Ders: Multi-Container

### 📗Bu bölümde Multi-Container Pod Yönetim işlemlerini bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
kubectl version
```
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
***
```
kubectl run k8s-pod-1 --image=hello-world
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl get pods
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl get deployment
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
kubectl get all
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl describe deployment
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl logs k8s-pod-1
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl run k8s-pod-2 --image=docker.io/murataksunet/k8s-hellothere --restart=Never
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl delete pods k8s-pod-1
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl delete pods --all
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl delete deployment x.yml
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl exec -it k8s-web-1 -- /bin/bash
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl exec k8s-web-1 -- ls -l
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl cp password.txt k8s-cp-1:tmp/
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl cp default/k8s-cp-1:/tmp/store/
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl port-forward mypod 8080:80
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl get po --show-labels
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl run k8s-label-2 --image=nginx --labels="env=prod,tier=frontend"
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl get po k8s-label-1 --show-labels
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl label pods k8s-label-1 env=demo --overwrite
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl label pods --all status=healthy
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl get po --selector="env=prod"
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl get po -l "env!=prod,tier=backend"
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl get po -l "env in (prod),tier in (frontend)"
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl delete pods -l "env=demo"
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl delete pods -l "env in (prod),tier in (backend)"
```
