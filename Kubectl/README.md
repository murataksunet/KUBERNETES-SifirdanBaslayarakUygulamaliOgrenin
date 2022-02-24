## 🧑 Ders: Kubectl Config

### 📗Bu bölümde Kubectl Config Yönetim işlemlerini bulacaksınız📗

#### Kubectl Varlığını Kontrol Et
***
```
kubectl version --short
```
#### Kubectl Yoksa Kur
***
```
curl "https://dl.k8s.io/release/v1.23.0/bin/windows/amd64/kubectl.exe"
veya
https://dl.k8s.io/release/v1.23.0/bin/windows/amd64/kubectl.exe
```
***
#### kubeconfig dosyasını görüntüle
```
kubectl config view
```
***
#### kubeconfig'deki tüm clusterları görüntüle
```
kubectl config get-clusters
```
***
#### kubeconfig'deki aktif olan config(*) bul
```
kubectl config get-contexts
```
***
#### kubeconfig'deki tüm userlerı görüntüle
```
kubectl config get-users
```
***
#### Developer cluster ortamına geçiş yap
```
kubectl config use-context developer
```
***
#### Aktif contexti görüntüle
```
kubectl config current-context
```
***
#### kubeconfig doyasını sadece aktif context olacak şekilde görüntüle
```
kubectl config view --minify
```
***
#### Config Silin
```
kubectl config delete-cluster research
kubectl config delete-context research
kubectl config delete-user research
```
***
#### Minikube üzerindeki tüm cluster profilleri silin ve yeni bir cluster oluşturun 
```
minikube delete --all
minikube start
```
