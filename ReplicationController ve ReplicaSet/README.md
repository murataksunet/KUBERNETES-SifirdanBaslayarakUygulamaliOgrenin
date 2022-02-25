## 🧑 Ders: ReplicationController ve ReplicaSet

### 📗Bu bölümde ReplicationController ve ReplicaSet Yönetim İşlemlerini Bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
apiVersion: v1
kind: ReplicationController
metadata:
  name: myrepc
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl get replicationcontroller
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl describe rc myrepc
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
kubectl delete replicationcontroller/myrepc
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl scale replicationcontroller myrepc --replicas=10
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl edit replicationcontroller/rcontroller001
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: myreps
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl get replicaset
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl describe rs myreps
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl delete rs/myreps
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl scale replicaset myreps --replicas=10
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl edit replicaset/myreps
```
