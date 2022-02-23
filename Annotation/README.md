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
#### Komut satırı üzerinden 
```
kubectl annotate pod mysql email="admin@murataksu.net"
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl top pods -A
```
