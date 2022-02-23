## 🧑 Ders: Namespace

### 📗Bu bölümde YAML dosyası üzerinden Namespace Pod Yönetim işlemlerini bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
default
kube-system
kube-public
Kube-node-lease
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
# kubectl create namespace dev
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl run nginx --image=nginx --namespace=<insert-namespace-name-here>
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl get pods --namespace=<insert-namespace-name-here>
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl port-forward multipod 8080:80
```
