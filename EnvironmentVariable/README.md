## 🧑 Ders: Environment Variable


### 📗Bu bölümde Environment Variable Yönetim işlemlerini bulacaksınız📗

#### Nedir ?
***
```
Envieronment Variable, POD içerisinde ortam değişkenleri tanımlamak için kullanılmaktadır
```
***
#### Pod içerisindeki Kubernetes environment variables
```
NODE_VERSION=4.4.2
EXAMPLE_SERVICE_PORT_8080_TCP_ADDR=10.3.245.237
HOSTNAME=envar-demo
...
DEMO_GREETING=Hello from the environment
DEMO_FAREWELL=Such a sweet sorrow

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
***
#### Pod detaylarında ENV bilgilerini görüntüleme
```
kubectl describe pod nginx-env 
```

