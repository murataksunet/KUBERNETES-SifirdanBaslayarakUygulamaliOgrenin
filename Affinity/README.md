## 🧑 Ders: Affinity

### 📗Bu bölümde Affinity Yönetim işlemlerini bulacaksınız📗

#### Node üzerine label atama
***
```
kubectl label node minikube-m03 disktype=ssd
```
***
#### Nodelar üzerinde bulunan labelları listeleme
```
kubectl get node minikube-m03 --show-labels
```
***
#### YAML dosyasında , podun talep edilen node üzerinde oluşturulması için, label bilgisinin yazılması
```
  nodeSelector:
    disktype: ssd
```
***
#### POD'un talep edilen node üzerinde oluşturulduğunun kontrolü
```
kubectl get pods -o wide
```
