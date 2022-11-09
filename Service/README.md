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
#### Pod nesnesi için service nesnesi expose etme
```
kubectl expose pod/my-nginx
```
***
#### Deployment nesnesi için LoadBalancer service nesnesi expose etme 
```
kubectl expose deployment myweb --port 80 --type=LoadBalancer
```
***
#### Deployment'in expose edilmesi ve imperative yöntemle service objesinin oluşturulması
```
Ör: kubectl expose deployment frontend --type=ClusterIP --name=frontend
```
***
#### Sistemde tanımlı Service nesnelerinin listelenmesi
```
kubectl get svc
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
***
#### Service objelerinin silinmesi
```
kubectl delete service frontend
```
