## 🧑 Ders: Hardware-Limit

### 📗Bu bölümde POD Hardware-Limit Yönetim işlemlerini bulacaksınız📗

#### YAML dosyası hardware limit detayları
***
```
    resources:
      requests:           ## Node üzerinde olması istenilen hardware limit
        cpu: 100m
        memory: 128Mi
      limits:             ## Hardware'in kullanabileceği üst limit
        cpu: 250m
        memory: 256Mi
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
