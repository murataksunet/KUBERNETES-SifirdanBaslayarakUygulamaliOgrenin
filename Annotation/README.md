## 🧑 Ders: Annotation

### 📗Bu bölümde Annotation Yönetim işlemlerini bulacaksınız📗

#### Nedir ?
***
```
Annotation, Kubernetes nesneleri üzerinde ek açıklamalar yapmak için kullanılmaktadır. Burada girilen değerler Kubernetes’in umurunda değildir
```
***
#### YAML üzerinden Annotation Ekleme
```
metadata:
  name: mysql
  labels:
    db: mysql
  annotations:
    owner: "Murat AKSU"
    releasedate: "01.01.2023"
    version: "1.1.0"
    imageregistry: "https://hub.docker.com"
    kbarticle: "https://kb.docs.example.com/KB123456"
```
***
#### Komut satırından Pod üzerine annotate ekleme 
```
kubectl annotate pod mysql email="admin@murataksu.net"
```
***
#### annotate bilgisi güncelleme
```
kubectl annotate pod mysql version="2" --overwrite
```
***
#### annotate kaldırma
```
kubectl annotate pod mysql kbarticle-
```
***
#### Service üzerine annotate ekleme
```
kubectl annotate service quote a8r.io/owner=”@sally”
```
***
#### annotate bilgisi görüntüleme
```
kubectl describe pod mysql
```
