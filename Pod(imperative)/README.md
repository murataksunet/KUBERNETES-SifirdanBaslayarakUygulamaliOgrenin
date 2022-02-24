## 🧑 Ders: Kubectl(imperative)

### 📗Bu bölümde Kubectl(imperative) Yönetim işlemlerini bulacaksınız📗

#### Kubernetes versiyon bilgisi öğrenme
***
```
kubectl version
```
#### Bağımsız nginx POD oluşturma
***
```
kubectl run k8s-pod-1 --image=nginx
```
***
#### Sistemde tanımlı POD'ları listeleme
```
kubectl get pods
```
***
#### Sistemde tanımlı Deployment'ları listeleme
```
kubectl get deployment
```
***
#### Sistemde tanımlı tüm nesneleri listeleme
```
kubectl get all
```
***
#### myproject-dep nesnesinin detaylarını görüntüle
```
kubectl describe deployment myproject-dep
```
***
#### Pod logları görüntüle
```
kubectl logs k8s-pod-1
```
***
#### Özel image kullanarak POD oluşturma
```
kubectl run k8s-pod-2 --image=docker.io/murataksunet/k8s-hellothere --restart=Never
```
***
#### POD silme
```
kubectl delete pods k8s-pod-1
```
***
#### Default namespace de çalışan tüm podları silme
```
kubectl delete pods --all
```
***
#### YAML config file üzerinden nesne silme
```
kubectl delete deployment x.yml
```
***
#### Çalışan POD içerisine giriş yapma
```
kubectl exec -it k8s-web-1 -- /bin/bash
```
***
#### Çalışan pod içerisine girmeden ana dizini listeleme
```
kubectl exec k8s-web-1 -- ls -l
```
***
#### Lokaldeki password.txt dosyasını POD içerisine kopyalama
```
kubectl cp password.txt k8s-cp-1:tmp/
```
***
#### POD içerisindeki dizindeki dosyaları lokale kopyalama
```
kubectl cp default/k8s-cp-1:/tmp/store/
```
***
#### POD üzerine port yönlendirme 
```
kubectl port-forward mypod 8080:80
```
***
#### Sistemdeki POD ları label'ları ile birlikte listele 
```
kubectl get po --show-labels
```
***
#### Label ataması yapılarak POD oluşturma  
```
kubectl run k8s-label-2 --image=nginx --labels="env=prod,tier=frontend"
```
***
#### Özel POD'a ait labelları listeleme
```
kubectl get po k8s-label-1 --show-labels
```
***
#### POD üzerinde bulunan label bilgisini değiştirme
```
kubectl label pods k8s-label-1 env=demo --overwrite
```
***
#### Sistemde çalışan tüm POD lar üzerine toplu label ataması yapma 
```
kubectl label pods --all status=healthy
```
***
#### Selector kullanarak label üzerinden POD sorgulama
```
kubectl get po --selector="env=prod"
```
***
#### Selector kullanarak label üzerinden POD sorgulama
```
kubectl get po -l "env!=prod,tier=backend"
```
***
#### Selector kullanarak label üzerinden POD sorgulama
```
kubectl get po -l "env in (prod),tier in (frontend)"
```
***
#### Selector kullanarak label üzerinden POD sorgulama
```
kubectl delete pods -l "env=demo"
```
***
#### Selector kullanarak label üzerinden POD sorgulama
```
kubectl delete pods -l "env in (prod),tier in (backend)"
```
