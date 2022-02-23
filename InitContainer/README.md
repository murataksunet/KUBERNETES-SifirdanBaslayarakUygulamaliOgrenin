## 🧑 Ders: Init-Container

### 📗Bu bölümde Init-Container Pod Yönetim işlemlerini bulacaksınız📗

#### Pod içerisinde main container ayağa kalkmadan önce diğer containerın çalışması 
***
```
Name:          myapp-pod
Namespace:     default
[...]
Labels:        app=myapp
Status:        Pending
[...]
Init Containers:
  init-myservice:
[...]
    State:         Running
[...]
  init-mydb:
[...]
    State:         Waiting
      Reason:      PodInitializing
    Ready:         False
[...]
Containers:
  myapp-container:
[...]
    State:         Waiting
      Reason:      PodInitializing
    Ready:         False
[...]
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl exec my-pod -c my-container -- ls / 
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl logs my-pod -c my-container 
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
kubectl logs -l name=myLabel -c my-container 
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl port-forward multipod 8080:80
```
