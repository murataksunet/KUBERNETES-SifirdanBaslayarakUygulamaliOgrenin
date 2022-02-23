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





#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
kubectl get po --show-labels
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl describe pod tomcat-labelpod-1
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version="9.0" 
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version="9.0" --overwrite
```
