
## 📗📗Bu bölümde Declerative yöntemde YAML dosya detaylarını ve komut kullanım şekillerini bulacaksınız📗📗

#### Template YAML dosyası 
***
```
apiVersion:
kind:
metadata:
spec:
```
***
Pod Nesnesi Oluşturma ve Pod'a firstyaml ismi verme
```
Pod ismini firstyaml olarak verin
apiVersion: v1
kind: Pod
metadata:
  name: firstyaml
spec:
```
***
Apache Image'ini Kullanan Pod Nesnesi Oluşturma
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
Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve Podun 80 Portunu Açma
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
