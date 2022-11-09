## 🧑 Ders: Taint Toleration

### 📗Bu bölümde Taint&Toleration Yönetim işlemlerini bulacaksınız📗

#### Node üzerine Label bilgisi atama
***
```
kubectl label nodes minikube-m03 dedicated=devops
```
***
#### Node üzerine taint bilgisi atama
```
kubectl taint nodes minikube-m03 cpu_speed=fast:NoSchedule
```
***
#### Node üzerine taint bilgisi atama ve effect türleri
```
kubectl taint nodes node1 key1=value1:NoSchedule
kubectl taint nodes node1 key1=value1:PreferNoSchedule
kubectl taint nodes node1 key1=value1:NoExecute
```
***
#### Node üzerinde label ve taint bilgilerini görüntüle
```
kubectl describe nodes minikube-m03
```
***
#### Node üzerindeki taint bilgisini çıkarma
```
kubectl taint nodes minikube-m03 cpu_speed-
```
***
#### POD üzerine tolerations bilgisi ekleme - hardware=special olmalı
```
tolerations:
- key: "hardware"
  operator: "Equal"
  value: "special"
  effect: "NoSchedule"
```
***
#### POD üzerine tolerations bilgisi ekleme - node üzerinde taint olarak "memorysize" bilgisi olması yeterli
```
tolerations:
- key: "memorysize"
  operator: "Exists"
  effect: "NoSchedule"
```
