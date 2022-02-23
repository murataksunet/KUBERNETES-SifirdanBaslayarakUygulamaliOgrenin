## 🧑 Ders: Kurulum (Minikube-Kubeadm)

### 📗Bu bölümde Minikube-Kubeadm Detaylarını bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
# minikube status // minikube durum bilgisini görüntüleyin
# minikube node list // minikube node listleme yapın
# minikube delete  // minikube üzerindeki lokal cluster'ı silin


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
