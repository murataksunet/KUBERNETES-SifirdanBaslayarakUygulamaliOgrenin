## 🧑 Ders: ReplicationController ve ReplicaSet

### 📗Bu bölümde ReplicationController ve ReplicaSet Yönetim İşlemlerini Bulacaksınız📗

#### YAML dosyası üzerinden ReplicationController nesnesi tanımlama
***
```
apiVersion: v1
kind: ReplicationController
metadata:
  name: myrepc
```
***
#### Sistemde tanımlı replicationcontroller nesnelerini listele
```
kubectl get replicationcontroller
```
***
#### Replicationcontroller nesnesi detaylarını görüntüle
```
kubectl describe rc myrepc
```
***
#### Replicationcontroller nesnesi silme
```
kubectl delete replicationcontroller/myrepc
```
***
#### Replicationcontroller nesnesi pod sayısı ölçeklendirme
```
kubectl scale replicationcontroller myrepc --replicas=10
```
***
#### Replicationcontroller nesnesi config düzenleme
```
kubectl edit replicationcontroller/rcontroller001
```
***
#### YAML dosyası üzerinden ReplicaSet nesnesi tanımlama
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: myreps
```
***
#### Sistemde tanımlı ReplicaSet nesnelerini listeleme
```
kubectl get replicaset
```
***
#### ReplicaSet nesnesi detaylarını görüntüle
```
kubectl describe rs myreps
```
***
#### ReplicaSet nesnesi silme
```
kubectl delete rs/myreps
```
***
#### ReplicaSet nesnesi pod sayısı ölçeklendirme
```
kubectl scale replicaset myreps --replicas=10
```
***
#### ReplicaSet nesnesi config düzenleme
```
kubectl edit replicaset/myreps
```
