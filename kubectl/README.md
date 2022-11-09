## 🧑 Ders: kubectl

### 📗Bu bölümde "kubectl" komut kullanımı bulacaksınız📗(murataksu.net)

#### Kubectl komut yazım şekli
***
```
kubectl [command] [TYPE] [NAME] [flags]
```
***
#### Kubectl versiyon bilgisini görüntüleme
```
kubectl version
```
***
#### Kubectl versiyon bilgisini kısa görüntüleme
```
kubectl version –short
```
***
#### Cluster detaylarını görüntüleme
```
kubectl cluster-info
```
***
#### Desteklenen API sürümlerini görüntüleme
```
kubectl api-versions
```
***
#### Cluster içerisindeki tüm nodeları listeme
```
kubectl get nodes
```
***
#### Default namespacedeki tüm podları listeleme
```
# kubectl get pods
Not: Demo ortamızda nesne yoksa test amaçlı deployment nesnesi oluşturabilirsiniz
kubectl create deployment my-dep-demo --image=nginx --scale=10
```
***
#### Default namespace’deki tüm replicasetleri listeleme
```
kubectl get replicaset
```
***
#### Default namespace’deki tüm deployment’ları listeleme
```
kubectl get deployment
```
#### Default namespace’deki tüm pod,replicaset ve deployment’ları tek komutla listeleme
```
kubectl get po,rs,deploy
```
***
#### Tüm namespace'lerde bulunan podları listeleme (--all-namespaces ifadesinin kısaltması -A'dır.Tüm namespace'ler anlamına gelir)
```
kubectl get pods --all-namespaces
```
***
#### Default namespace’deki tüm pod’ları ada göre sıralayarak listeleme
```
kubectl get pods --sort-by=.metadata.name
```
***
#### Default namespace’deki tüm pod’ları yeniden başlatma sayısına göre listeleme
```
kubectl get pods --sort-by=.status.containerStatuses[0].restartCount
```
***
#### --output parametresiyle (kısaltması -o 'dur) çıktı talep edilen farklı bir formatta döndürülebilir. 
```
Örn: Default namespace’deki tüm pod’ların sadece isimlerini listeleme
kubectl get pods --output name

-o yaml YAML formatında çıktı döndürür
-o json JSON formatinda çıktı döndürür
-o wide çıktıyı detay bilgi şekilde döndürür 
-o jsonpath=<template> Jsonpath ifadesinde tanımlanan alanları döndürür
-o name Sadece isimleri döndürür
-o custom-columns=<spec> Comma-Seperated kolonlardan bir table döndürür
```
***
#### Default namespace’deki tüm pod’ları ek bilgilerle listeleme (IP adresi,node ismi vb)
```
kubectl get pods --output wide
```
***
#### Default namespace’deki tüm pod’ları YAML formatında görüntüleme
```
kubectl get pods --output yaml
```
***
#### my-pod isimli nesneyi yaml formatında görüntüleme
```
kubectl get po my-pod -o yaml
```
***
#### my-pod isimli nesneyi json formatında görüntüleme
```
kubectl get po my-pod -o json
```
***
#### my-pod isimli nesneyi yaml formatı haline getirip my-pod.yaml ismiyle dışarıya aktarma
```
kubectl get po my-pod -o yaml >> my-pod.yaml
```
***
#### Tüm namespace’lerde ki podların kullandığı image bilgisini görüntüleme
```
kubectl get pods -A -o=custom-columns='DATA:spec.containers[*].image'
```
***
#### Tüm namespace’lerde ki podların metadata aldındaki tüm bilgilerini görüntüleme
```
kubectl get pods -A -o=custom-columns='DATA:metadata.*'
```
***
#### Default namespace’deki tüm pod’ların image bilgisini görüntüleme
```
kubectl get pods --namespace default --output=custom-columns="NAME:.metadata.name,IMAGE:.spec.containers[*].image"
```
***
#### mypod isimli podun container ismi ve image bilgisini görüntüleme
```
kubectl get pod mypod -o custom-columns=CONTAINER:.spec.containers[0].name,IMAGE:.spec.containers[0].image
```
***
#### Tüm namespacelerdeki podların container isimlerini ve image bilgilerini görüntüleme
```
kubectl get pod -A -o custom-columns=CONTAINER:.spec.containers[0].name,IMAGE:.spec.containers[0].image
```
***
#### Tüm nodeların ExternalIP adreslerini görüntüleme
```
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=ExternalIP)].address}'
```
***
#### my-pod isimli pod içerisindeki tüm container isimlerini görüntüle
```
kubectl get pods my-pod -o jsonpath='{.spec.containers[*].name}'
```
***
#### Clusterdaki tüm node’ları ayrıntılarıyla birlikte listeleme
```
kubectl describe nodes
```
***
#### Default namespace’deki tüm pod’ları ayrıntılarıyla birlikte listeleme
```
kubectl describe pods 
```
***
#### my-pod isimli pod’u ayrıntılı bir şekilde görüntüleme 
```
kubectl describe pods/my-pod 
```
***
#### my-dep-demo isimli deployment nesnesini ayrıntılı olarak görüntüleme
```
kubectl describe deploy my-dep-demo
```
***
#### my-rc isimli replicaset nesnesini ayrıntılı olarak görüntüleme
```
kubectl describe rc my-rc
```
***
#### Pod nesnesi belgesini görüntüleme
```
kubectl explain pod
```
***
#### Deployment nesnesi belgesini görüntüleme
```
kubectl explain deployment
```
***
#### Belirli bir alanın belgesini görüntüleme
```
kubectl explain deployment.spec –recursive
```
