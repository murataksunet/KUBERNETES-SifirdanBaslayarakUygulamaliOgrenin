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
#### Init Container durumlarına kontrol etme
```
kubectl get pod nginx --template '{{.status.initContainerStatuses}}'
```
***
#### Pod içerisindeki init-mydb loglarının listelenmesi
```
kubectl logs <pod-name> -c <init-container-2>
```
***
#### Pod içerisindeki init-mydb loglarının listelenmesi
```
kubectl logs --container=init-mydb initpod
```
***
#### InitContainer Status Anlamları
```
Status	Meaning
Init:N/M	The Pod has M Init Containers, and N have completed so far.
Init:Error	An Init Container has failed to execute.
Init:CrashLoopBackOff	An Init Container has failed repeatedly.
Pending	The Pod has not yet begun executing Init Containers.
PodInitializing or Running	The Pod has already finished executing Init Containers.
```
