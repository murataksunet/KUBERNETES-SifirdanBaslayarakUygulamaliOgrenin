## 🧑 Ders: Deployment

### 📗Bu bölümde Deployment nesnesi yönetim işlemlerini bulacaksınız📗

#### YAML dosyası hardware limit detayları
***
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mydeploy
```
#### YAML Hardware detayları
***
```
kubectl get deployments/nginx-deployment
```
#### Pod'un kullandığı CPU-MEMORY kulllanım değerini görüntüleme
***
```
kubectl describe deploy/nginx-deployment
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl scale deployment/nginx-deployment --replicas=10
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl delete deploy/nginx-deployment
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl edit deployment/nginx-deployment
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl set image deployment/nginx-deployment nginx-cnt=nginx:1.16.1
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl set image deployment/nginx-deployment nginx-cnt=nginx:1.16.1
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl rollout status deployment/nginx-deployment
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl rollout history deployment/nginx-deployment
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl rollout undo deployment/nginx-deployment
```
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
***
```
kubectl logs deploy/my-deployment 
```
