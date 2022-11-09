## 🧑 Ders: Annotation

### 📗Bu bölümde Annotation Yönetim işlemlerini bulacaksınız📗(murataksu.net)

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
#### Komut satırından Pod üzerine Annotation ekleme 
```
kubectl annotate pod mysql email="info@murataksu.net"
```
***
#### Annotation bilgisi güncelleme
```
kubectl annotate pod mysql version="2" --overwrite
```
***
#### Annotation kaldırma
```
kubectl annotate pod mysql kbarticle-
```
***
#### Service üzerine Annotation ekleme
```
kubectl annotate service quote a8r.io/owner=”@sally”
```
***
#### Annotation bilgisi görüntüleme
```
kubectl describe pod mysql
```

