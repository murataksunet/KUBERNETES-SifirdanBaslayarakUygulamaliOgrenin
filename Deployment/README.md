## 🧑 Ders: Deployment

### 📗Bu bölümde Deployment nesnesi yönetim işlemlerini bulacaksınız📗

#### Deployment nesnesi oluşturma
***
```
kubectl create deployment my-dep --image=busybox
```
#### Komut ile Deployment nesnesi oluşturma
***
```
kubectl create deployment my-dep --image=busybox -- date
```
#### 3 kopyalı deployment nesnesi oluşturma
***
```
kubectl create deployment my-dep --image=nginx --replicas=3
```
#### YAML dosyası üzerinden Deployment nesnesi oluşturma
***
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mydeploy
```
#### Sistemde tanımlı Deployment'ları listeleme 
***
```
kubectl get deployments
```
#### Sistemde tanımlı Deployment nesnesi detaylarını görüntüleme
***
```
kubectl describe deploy/mydeploy
```
#### Deployment nesnesi ölçeklendirme
***
```
kubectl scale deployment/mydeploy --replicas=10
```
#### Deployment nesnesi silme
***
```
kubectl delete deploy/mydeploy
```
#### Deployment nesnesi detaylarına bakma
***
```
kubectl logs deploy/mydeploy
```
#### Deployment nesnesi config dosyası düzenleme
***
```
kubectl edit deployment/mydeploy
```
#### POD container image güncelleme
***
```
kubectl set image deployment/mydeploy nginx-cnt=nginx:1.16.1
```
#### Image güncelleme durumu kontrol etme
***
```
kubectl rollout status deployment/mydeploy
```
#### Image revisyon geçmişini kontrol etme
***
```
kubectl rollout history deployment/mydeploy
```
#### Önceki image revizyonlarına geri dönme
***
```
kubectl rollout undo deployment/mydeploy
```
#### Önceki belirlenen image revizyonlarına geri dönme
***
```
kubectl rollout undo deployment/app --to-revision=2
```
