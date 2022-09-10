## 🧑 Ders: Secret

### 📗Bu Bölümde Secret Detayları Hakkında Bilgiler Bulacaksınız📗

#### Boş Secret Nesnesi Oluşturma
***
```
kubectl create secret generic empty-secret
```
***
#### Secret Nesnesi Oluşturma
```
kubectl create secret generic app-passwd --from-literal=mypassword='onetwothree123!'
```
***
#### YAML File Üzerinden Secret Nesnesi Oluşturma
```
apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  username: YWRtaW4=
  password: MWYyZDFlMmU2N2Rm
```
***
#### Secret Nesnesi Oluşturma
```
kubectl create secret generic db-user-pass --from-file=dbuname=./username.txt --from-file=dbupassword=./password.txt
```
***
#### Secret Nesnesi Oluşturma
```
kubectl create secret generic db-user-pass --from-literal=username=devuser --from-literal=password='S!B\*d$zDsb='
```
***
#### Secret Detaylarını Görüntüle
```
kubectl describe secrets/db-user-pass
```
***
#### Secret Nesnesi Sil
```
kubectl delete secret db-user-pass
```

