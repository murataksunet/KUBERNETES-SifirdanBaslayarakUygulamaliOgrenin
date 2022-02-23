## 🧑 Ders: Label-Selector

### 📗Bu bölümde Label-Selector kullanarak Pod Yönetim işlemlerini bulacaksınız📗

***
#### Equality-based requirement
```
environment = production
tier != frontend
```
***
#### Set-based requirement
```
environment in (production, qa)
tier notin (frontend, backend)
```
***
#### Pod'a Label Atama
```
kubectl label pods web-nginx tier=frontend
```
***
#### Node'a Label Atama
```
kubectl label nodes node1 disktype=ssd
```
***
#### Pod'a Label Atama
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version="9.0" 
```
***
#### Label olan Pod üzerinde değişiklik yapma
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version="9.0" --overwrite
```
#### Podlara atanan labelları listeleme
***
```
kubectl get po --show-labels
```
***
#### Pod üzerinde bulunan labelları görüntüleme
```
kubectl describe pod tomcat-labelpod-1
```
#### Podlara atanan labelları listeleme
***
```
kubectl get po --show-labels
```
***
#### Pod üzerinde bulunan labelları görüntüleme
```
kubectl describe pod tomcat-labelpod-1
```
