## 🧑 Ders: Secret

### 📗Bu Bölümde Secret Detayları Hakkında Bilgiler Bulacaksınız📗

#### Secret Nesnesi Oluşturma
***
```
kubectl create secret generic "secret-ismi" --from-literal="anahtar"="değer" --from-file="anahtar"="değerin-okunacagi-dosya" --from-file="değerin-okunacagi-dosya"
```
#### Boş Secret Nesnesi Oluşturma
***
```
kubectl create secret generic empty-secret
```
***
#### Tanım üzerinden Secret Nesnesi Oluşturma
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
#### Path üzerinden dosya içieri ile Secret Nesnesi Oluşturma
```
kubectl create secret generic db-user-pass --from-file=dbuname=./username.txt --from-file=dbupassword=./password.txt
```
***
#### Birden fazla tanımlı Secret Nesnesi Oluşturma
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

