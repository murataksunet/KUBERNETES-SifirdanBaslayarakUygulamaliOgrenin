
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
kubectl apply -f ./my1.yaml -f ./my2.yaml    ### Birden fazla YAML dosyasındaki nesneleri oluştur
kubectl apply -f ./dir                       ### Dizindeki YAML dosyalarındaki nesneleri oluştur
kubectl apply -f https://git.io/vPieo        ### URL üzerinde ki YAML dosyasındaki nesneleri oluştur
kubectl create -f ./my-manifest.yaml         ### YAML dosyasındaki nesneleri oluştur. YAML dosyası güncellemesinde uyarı verir
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```
kubectl run firstyaml --image=httpd --dry-run=client -o yaml > thirdyaml.yaml
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```
kubectl run mypod --image=alpine:3.9 --restart=Never --dry-run=client --command -o yaml -- sleep 3600 > command-sleep-2.yaml
kubectl run command-arg --image=busybox --restart=Never --dry-run=client -o yaml --command -- printenv HOSTNAME KUBERNETES_PORT > command-arg-3.yaml
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```
kubectl get pod mypod -o 'jsonpath={.spec.containers[*].name}'
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```
kubectl get pod mypod -o custom-columns=CONTAINER:.spec.containers[0].name,IMAGE:.spec.containers[0].image
kubectl get pod -A -o custom-columns=CONTAINER:.spec.containers[0].name,IMAGE:.spec.containers[0].image
```
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```
kubectl get pods -A --sort-by=.metadata.name
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
***
#### Apache Image'ini Kullanan Pod Nesnesi Oluşturma ve 80 Portunu Açma
```

```
