## 🧑 Ders: Environment Variable


### 📗Bu bölümde Environment Variable Yönetim işlemlerini bulacaksınız📗(murataksu.net)

#### Nedir ?
***
```
Envieronment Variable, POD içerisinde ortam değişkenleri tanımlamak için kullanılmaktadır.

Örnek:
BACKEND_SRV_SERVICE_HOST = 10.147.252.185
BACKEND_SRV_SERVICE_PORT = 5000
KUBERNETES_RO_SERVICE_HOST = 10.147.240.1
KUBERNETES_RO_SERVICE_PORT = 80
KUBERNETES_SERVICE_HOST = 10.147.240.2
KUBERNETES_SERVICE_PORT = 443
KUBE_DNS_SERVICE_HOST = 10.147.240.10
KUBE_DNS_SERVICE_PORT = 53
```
***
#### Pod Oluştururken ENV bilgisi ekleme
```
kubectl run nginx-env --image=nginx --restart=Always --env=KUBERNETES_SERVICE_PORT="443"
```
***
#### Çalışan POD üzerindeki ENV bilgilerini görüntüleme
```
kubectl exec nginx-env -- printenv
```
***
#### YAML üzerinden ENV bilgisi ekleme
```
    env:
    - name: PMA_HOST
      value: mysql
    - name: PMA_PORT
      value: "3306"
```

