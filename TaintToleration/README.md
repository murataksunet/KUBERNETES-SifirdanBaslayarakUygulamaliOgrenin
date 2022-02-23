## 🧑 Ders: Taint Toleration

### 📗Bu bölümde Taint Toleration Yönetim işlemlerini bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
kubectl label nodes minikube-m03 dedicated=devops
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl taint nodes minikube-m03 cpu_speed=fast:NoSchedule
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl describe nodes minikube-m03
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
kubectl taint nodes minikube-m03 cpu_speed-
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
  - key: "hardware"
    operator: "Equal"
    value: "special"
    effect: "NoSchedule"
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
  tolerations:
  - operator: "Exists"
```
