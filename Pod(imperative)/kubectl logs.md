## 🧑 Ders: Imperative Yöntemle POD Yönetimi

### 📗Bu bölümde "kubectl logs" komut kullanımını bulacaksınız📗(murataksu.net)

#### my-web isimli podun loglarını görüntüleme
***
```
kubectl logs my-web
```
***
#### my-web isimli podun log sıralamasını değiştirerek görüntüle
```
kubectl logs my-web --previous
```
***
#### my-web isimli podun loglarını akış olarak görüntüle
```
kubectl logs --follow my-web
```
***
#### my-web isimli podun loglarını en son 20 satırlık kısmını görüntüle
```
kubectl logs --tail=20 my-web
```
***
#### my-web isimli podun loglarını son 1 saatlik kısmını götüntüle
```
kubectl logs --since=1h my-web
```
***
#### my-web isimli poddaki tüm container loglarını görüntüle
```
kubectl logs my-web --all-containers=true
```
