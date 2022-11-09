## 🧑 Ders: Namespace

### 📗Bu bölümde YAML dosyası üzerinde Namespace Pod Yönetim işlemlerini bulacaksınız📗(murataksu.net)

***
#### YAML dosyası üzerinden namespace oluşturma 
```
apiVersion: v1
kind: Namespace
metadata:
  name: developer
```
***
#### Komut satırı üzerinden namespace oluşturma
```
# kubectl create namespace developer
```
#### Sistem üzerinde tanımlı namespaceleri listele
```
# kubectl get namespace
```
#### Namespace detaylarını görüntüleme
```
# kubectl describe namespace developer
```
#### Kubernetes üzerinde dahili gelen namespaceler
***
```
default
kube-system
kube-public
Kube-node-lease
```
***
#### Tanımlı namespace üzerinde POD oluşturma
```
kubectl run nginx --image=nginx --namespace=developer
```
***
#### Namespace altındaki podları listeleme
```
kubectl get pods --namespace=developer
```
***
#### YAML dosyasındaki nesneleri Namespace altında oluşturma
```
# kubectl create -f  proje.yaml --namespace=developer
```
***
#### Namespace altındaki POD içerisine bağlanma
```
# kubectl exec -it proje --namespace=developer -- /bin/bash
```
***
#### Namespace altındaki POD u silme
```
# kubectl delete pod nginx -n developer
```
***
#### Namespace silme
```
# kubectl delete ns developer
```

