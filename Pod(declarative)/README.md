
### 📗📗Bu bölümde Declerative yöntemde YAML dosya detaylarını ve komut kullanım şekillerini bulacaksınız📗📗

Bir pod objesinin loglarını görüntüleme. 
***
```
apiVersion:
kind:
metadata:
spec:
```
***
Bir pod objesinin loglarını görüntüleme. 
```
Pod ismini firstyaml olarak verin
apiVersion: v1
kind: Pod
metadata:
  name: firstyaml
spec:
```
***
Bir pod objesinin loglarını görüntüleme. 
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
Bir pod objesinin loglarını görüntüleme. 
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
