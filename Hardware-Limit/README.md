## 🧑 Ders: Hardware-Limit

### 📗Bu bölümde POD Hardware-Limit Yönetim işlemlerini bulacaksınız📗(murataksu.net)

#### YAML dosyası hardware limit detayları
***
```
    resources:
      requests:           ## Node üzerinde olması istenilen kaynak değeri
        cpu: 100m
        memory: 128Mi
      limits:             ## Kullanabilecek üst limit
        cpu: 250m
        memory: 256Mi
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
***
#### Kubernetes node'lar üstünde ki cpu-memory kullanım değerlerini görüntüleme
```
kubectl top node 
```
