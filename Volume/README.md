## 🧑 Ders: Volume

### 📗Bu bölümde emptyDir ve HostPath yönetimi hakkında bilgi bulacaksınız📗

#### Pod içerisine emptyDir volume bağlama
***
```
  volumes:
  - name: cache-volume
    emptyDir: {}
```
***
#### Pod içerisine hostPath volume bağlama
```
  volumes:
  - name: data-volume
    hostPath:
      path: /tmp/storage
```
***
#### Pod'a bağlanan volume container içerisine mount etme
```
      volumeMounts:
        name: data-volume
      - mountPath: /usr/share/nginx/html


```
***
#### POD içerisinde ki volume bilgisini görüntüleme
```
kubectl describe pods volume-test
```


