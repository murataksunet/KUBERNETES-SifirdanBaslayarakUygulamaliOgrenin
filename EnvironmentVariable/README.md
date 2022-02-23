## 🧑 Ders: Environment Variable


### 📗Bu bölümde Environment Variable Yönetim işlemlerini bulacaksınız📗

#### Nedir ?
***
```
Envieronment Variable, POD içerisinde ortam değişkenleri tanımlamak için kullanılmaktadır
```
***
#### YAML Hardware detayları
```
spec.containers[].resources.limits.cpu
spec.containers[].resources.limits.memory
spec.containers[].resources.limits.hugepages-<size>
spec.containers[].resources.requests.cpu
spec.containers[].resources.requests.memory
spec.containers[].resources.requests.hugepages-<size>
```
***
#### Pod'un kullandığı CPU-MEMORY kulllanım değerini görüntüleme
```
kubectl top pod cpuramlimit-pod 
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl top pods -A
```
