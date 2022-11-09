## 🧑 Ders: minikube yönetim komutları

### 📗Bu bölümde "minikube" yönetim komutlarını bulacaksınız📗(murataksu.net)

#### Minikube versiyon bilgisini öğrenme
***
```
minikube version
```
***
#### Yeni cluster oluşturma
```
minikube start
```
***
#### Var olan lokal clusterı silme
```
minikube delete 
```
***
#### Cluster durumunu görüntüleme
```
minikube status 
```
***
#### Özel donanım limiti belirterek cluster oluşturma
```
minikube start --memory 5120 --cpus=4 
```
***
#### Özel kubernetes versiyon belirterek cluster oluşturma
```
 minikube start --kubernetes-version v1.11.0
```
***
#### Minikube harici yeni isimle farklı cluster oluşturma
```
minikube start -p mycluster
```
***
#### Minikube üzerindeki mevcut profilleri listeleme
```
minikube profile list
```
***
#### İki Node'lu yeni cluster oluşturma
```
minikube start --node 2 
```
#### Cluster içerisine yeni worker node ekleme
```
minikube node add  
```
***
#### Cluster içerisinde çalışan nodelari listeleme
```
minikube node list 
```
***
#### Tüm profil clusterı silme
```
minikube delete --all 
```
***
#### Cluster içerisinde bulunan tekil node silme
```
minikube node delete xxxxxxx 
```
***
#### Lokal clusterı durdurma
```
minikube stop
```
***
#### Kubernetes web arayüzü-dashboard ekranına bağlanma
```
minikube dashboard
```
***
#### Kubernetes web arayüzü-dashboard linkini öğrenme
```
minikube dashboard --url
```
***
#### Minikube sanal makinasına-host'una giriş yapma
```
minikube ssh 
```
***
#### Minikube üzerindeki imagelari listeleme
```
minikube image ls 
```
***
#### Minikube üzerindeki addonlari listeleme
```
minikube addons list 
```
***
#### Minikube ip bilgisini öğrenme
```
minikube ip
```
***
#### Minikube loglarını görüntüleme
```
minikube logs
```
***
#### Minikube güncellemesini kontrol etme
```
minikube update-check
```
