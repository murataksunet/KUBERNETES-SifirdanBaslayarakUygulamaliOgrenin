## 🧑 Ders: Service

### 📗Bu bölümde Service Nesnesi Yönetim işlemlerini bulacaksınız📗 (murataksu.net)

***
#### YAML dosyası üzerinden service nesnesi tanımlama
```
apiVersion: v1
kind: Service
metadata:
  name: my-service
```
***
#### Pod nesnesi için service nesnesi tanımlama
```
kubectl expose pod/my-nginx
```
***
#### Deployment nesnesi için LoadBalancer service nesnesi tanımlama
```
kubectl expose deployment myweb --port 80 --type=LoadBalancer
```
***
#### my-nginx service nesnesini listeleme
```
kubectl get svc my-nginx
```
***
#### my-nginx service nesnesi detaylarını görüntüleme
```
kubectl describe svc my-nginx
```
***
#### my-dep nesnesi için oluşturulan endpointleri listele 
```
kubectl get ep my-dep
```



