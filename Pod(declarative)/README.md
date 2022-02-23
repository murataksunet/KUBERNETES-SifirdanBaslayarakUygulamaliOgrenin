
***
Imperative yöntemle pod oluşturma.

```
apiVersion:
kind:
metadata:
spec:
```
Pod ismini firstyaml olarak verin
apiVersion: v1
kind: Pod
metadata:
  name: firstyaml
spec:
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
Bir pod objesinin loglarını görüntüleme. _(-f opsiyonu çıktıya yapışmanızı ve anlık olarak üretilen logları görmenizi sağlar)_
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
