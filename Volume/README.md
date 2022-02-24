## 🧑 Ders: Volume

### 📗Bu bölümde emptyDir ve HostPath Yönetim işlemleri Hakkında Bilgi bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
kubectl exec -it multipod -c container1 -- bash
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
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
kubectl logs -l name=myLabel -c my-container 
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
kubectl port-forward multipod 8080:80
```
