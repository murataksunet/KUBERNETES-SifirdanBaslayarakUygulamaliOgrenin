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
#### Pod içerisindeki init-mydb loglarının listelenmesi
```
kubectl logs --container=init-mydb initpod
```
***
#### Pod nesnesinin silinmesi
```
kubectl delete -f initcontainer.yaml
```
