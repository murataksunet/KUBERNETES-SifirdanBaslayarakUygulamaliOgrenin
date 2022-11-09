## 🧑 Ders: Deployment

### 📗Bu bölümde Deployment nesnesi yönetim işlemlerini bulacaksınız📗(murataksu.net)

#### Imperative yöntemle Deployment oluşturma

***
```
kubectl create deployment my-dep --image=busybox
```
#### 3 Pod kopyalı deployment nesnesi oluşturma
***
```
kubectl create deployment my-dep --image=nginx --replicas=3
```
#### Komut Çalıştırarak Deployment nesnesi oluşturma
***
```
kubectl create deployment my-dep --image=busybox -- date
```
#### Declarative yöntemle Deployment nesnesi oluşturma
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
kubectl delete deployment mydeploy
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
kubectl set image deployment/"deployment-ismi" "container-ismi"="yeni-imaj"  
Ör:kubectl set image deployment/mydeploy nginx-cnt=nginx:1.16.1
```
#### Image güncelleme durumunu kontrol etme
***
```
kubectl rollout status deployment/mydeploy
```
#### Deployment yapılan değişikliklerin listelenmesi
***
```
kubectl rollout history deployment/mydeploy
```
#### Deployment yapılan son değişikliğin geri alınması
***
```
kubectl rollout undo deployment/mydeploy
```
#### Önceki belirlenen image revizyonlarına geri dönme
***
```
kubectl rollout undo deployment/app --to-revision=2
```
#### Deployment üzerindeki değişikliklerin kaydı 
***
```
kubectl set image deployment/mydeploy nginx-cnt=nginx:1.16.1 --record=true 
```
#### Yapılan değişikliklerin durdurulması
***
```
kubectl rollout pause deployment mydeploy
```
#### Durdurulan rollout'un devam ettirilmesi
***
```
kubectl rollout resume deployment mydeploy
```
