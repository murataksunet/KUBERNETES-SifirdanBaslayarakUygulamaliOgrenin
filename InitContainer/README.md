## 🧑 Ders: Init-Container

### 📗Bu bölümde Init-Container Pod Yönetim işlemlerini bulacaksınız📗

#### Init-Container- Pod içerisinde main container ayağa kalkmadan önce diğer containerın öncelikli olarak çalıştırılması
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
#### Init Container durumlarını kontrol etme
```
kubectl get pod nginx --template '{{.status.initContainerStatuses}}'
```
***
#### Pod içerisindeki init containerın root dizini listeleme
```
kubectl exec pod/nginx --container c1 -- ls -l
```
***
#### Pod içerisindeki container loglarını listeleme
```
kubectl logs <pod-ismi> --container <init-container-ismi>
Ör:kubectl logs --container=init-mydb initpod
```
***
#### Label değeri app=sleep olan Pod içerisindeki init contailer'ların durumlarını json formayında görüntüleme
```
kubectl get pod -l app=sleep -o jsonpath='{.items[0].status.initContainerStatuses[*].name}'
```
***
#### InitContainer Status Anlamları
```
Status	Meaning
Init:N/M	The Pod has M Init Containers, and N have completed so far.
Init:Error	Bir Başlangıç Konteyneri çalıştırılamadı.
Init:CrashLoopBackOff	Bir Başlangıç Konteyneri tekrar tekrar başarısız oldu.
Pending	Henüz init containerı çalışmaya başlamadı.
PodInitializing or Running	Pod, ini-containerı çalıştımayı tamamladı
```
