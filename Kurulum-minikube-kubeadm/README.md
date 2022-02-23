## 🧑 Ders: Kurulum (Minikube-Kubeadm)

### 📗Bu bölümde Minikube-Kubeadm Detaylarını bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
# minikube status // minikube durum bilgisini görüntüleyin
# minikube node list // minikube node listleme yapın
# minikube delete  // minikube üzerindeki lokal cluster'ı silin
# minikube start -p mycluster-1 // minikube üzerinde mycluster-1 adında yeni cluster oluştur
# minikube start -p mycluster-2 --kubernetes-version=v1.15.0  // minikube üzerinde mycluster-2 versiyonu kubernetes 1.15.0
# minikube profile list  // minikube üzerinde oluşturduğumuz cluster profillerini listeleyin 
# minikube profile mycluster-1  // mycluster-1 profilini aktif hale getirin
# minikube delete --all // Oluşturduğunuz tüm profili silin
# minikube start // minikube üzerinde yeni bir lokal cluster oluşturun
# kubectl get nodes // kubectl üzerinden node listelemesi yapın
# minikube node add  // minikube üzerine yeni node ekle
# minikube node delete <node isim>  // minikube üzerinde yeni eklediğiniz nodu silin 
# minikube image ls  // minikube üzerindeki imagelari listeleyin
# minikube dashboard  // minikube üzerindeki Kubernetes dashboard ekranına erişin
# minikube cache list  // minikube üzerine lokalde cachede bulunan imageları listeleyin
# minikube addons list  // minikube üzerinde yerde alan addon'ları listeleyin
# minikube addons enable logviewer  // minikube üzerindeki logviewer addon'u aktif hale getirin
# minikube version  // minikube version bilgisi kontrol edin
# minikube update-check  //  minikube kubernetes güncel versiyon sorgulaması yapın
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
