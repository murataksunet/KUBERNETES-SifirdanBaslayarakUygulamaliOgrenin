## 🧑 Ders: Service

### 📗Bu bölümde Service Nesnesi Yönetim işlemlerini bulacaksınız📗

***
#### YAML dosyası service oluşturma
```
apiVersion: v1
kind: Service
metadata:
  name: my-service
```
***
#### YAML Hardware detayları
```
kubectl expose pod/my-nginx
```
***
#### Pod'un kullandığı CPU-MEMORY kulllanım değerini görüntüleme
```
kubectl expose deployment myweb --port 80 --type=LoadBalancer
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl get svc my-nginx
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl describe svc my-nginx
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl get ep my-nginx
```



