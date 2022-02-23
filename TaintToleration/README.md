## 🧑 Ders: Taint Toleration

### 📗Bu bölümde Taint Toleration Yönetim işlemlerini bulacaksınız📗

#### Node üzerine Label bilgisi atama
***
```
kubectl label nodes minikube-m03 dedicated=devops
```
***
#### Node üzerinde taint bilgisi atama
```
kubectl taint nodes minikube-m03 cpu_speed=fast:NoSchedule
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
#### POD üzerine tolerations bilgisi ekleme - memorysize key bilgisi olması yeterli
```
tolerations:
- key: "memorysize"
  operator: "Exists"
  effect: "NoSchedule"
```
