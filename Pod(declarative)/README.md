
## 📗Bu bölümde Declerative yöntemde YAML detaylarını ve komut kullanımı bulacaksınız📗

#### Template YAML dosyası 
***
```
apiVersion:
kind:
metadata:
spec:
```
***
#### Pod Nesnesi Oluşturma ve Pod'a firstyaml ismi verme
```
apiVersion: v1
kind: Pod
metadata:
  name: firstyaml
spec:
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma
```
apiVersion: v1
kind: Pod
metadata:
  name: firstyaml
spec:
  containers:
  - name: first-httpd-c1
    image: httpd
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```
apiVersion: v1
kind: Pod
metadata:
  name: firstyaml
spec:
  containers:
  - name: firsthttpdc1
    image: httpd
    ports:
    - containerPort: 80
```
***
#### YAML dosyası çalıştırma
```
kubectl apply -f ./my-manifest.yaml          ### YAML dosyasındaki nesneleri oluştur
kubectl apply -f ./my1.yaml -f ./my2.yaml
kubectl apply -f ./dir
kubectl apply -f https://git.io/vPieo
kubectl create -f ./my-manifest.yaml
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```

```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```

```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```

```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```

```
