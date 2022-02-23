## 🧑 Ders: Label-Selector

### 📗Bu bölümde Label-Selector kullanarak Pod Yönetim işlemlerini bulacaksınız📗

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
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl port-forward multipod 8080:80
```
