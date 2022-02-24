## 🧑 Ders: Persistent Volume

### 📗Bu bölümde Persistent Volume Yönetim işlemlerini bulacaksınız📗

#### Persistent Volume
***
```
Kubernetes Custer içerisinde herhangi bir node’a bağlı olmayan, kalıcı olarak veri depolamak için cluster’a bağladığımız komponente verilen isimdir
```
***
#### Persistent Volume Clam
```
spec.containers[].resources.limits.cpu
spec.containers[].resources.limits.memory
spec.containers[].resources.limits.hugepages-<size>
spec.containers[].resources.requests.cpu
spec.containers[].resources.requests.memory
spec.containers[].resources.requests.hugepages-<size>
```
***
#### Storage Class
```
kubectl top pod cpuramlimit-pod 
```
