## 🧑 Ders: Imperative Yöntemle POD Oluşturma

### 📗Bu bölümde Imperative yöntemde POD komut kullanımını bulacaksınız 📗(murataksu.net)

#### kubectl run komut yazım şekli
***
```
kubectl run NAME --image=image [--env="key=value"] [--port=port] [--dry-run=server|client] [--overrides=inline-json] [--command] -- [COMMAND] [args...]
```
***
#### my-web adında nginx image’ını kullanan pod oluşturma/çalıştırma
```
kubectl run my-web --image=nginx
```
***
#### hazelcast adında hazelcast image’ını kullanan, 5701 portu açılarak pod oluşturma/çalıştırma
```
kubectl run hazelcast --image=hazelcast --port=5701
```
***
#### my-web adında nginx image’ını kullanan pod oluşturmadan önizleme
```
kubectl run my-web --image=nginx --dry-run=client
```
***
#### my-web adında nginx image’ını kullanan pod yaml dosyasını ekrana çıktı alma
```
kubectl run my-web --image=nginx --dry-run=client -o yaml
```
***
#### my-web adında nginx image’ını kullanan pod yaml dosyasını mypod.yaml olarak çıktı alma
```
kubectl run my-web --image=nginx --dry-run=client -o yaml >> mypod.yaml
```
***
#### my-web adında nginx image’ını kullanan pod kapandığında yeniden başlatmama
```
kubectl run my-web --image=nginx --restart=Never
```
***
#### my-web isimli podu silme
```
kubectl delete pods my-web
```
***
#### Baz ve foo isimli podları ve servisleri silme
```
kubectl delete pod,service baz foo
```
#### Pod.yaml dosyasında ki nesneleri silme
```
kubectl delete -f pod.yaml
```
***
#### Default namespacedeki tüm podları silme
```
kubectl delete pods --all
```
***
#### Default namespacedeki oluşturulmuş tüm nesneleri silme
```
kubectl delete all --all
```
***
#### my-ns namespacedeki tüm podları ve servisleri silme
```
kubectl delete -n my-ns pod,svc --all
```
***
#### foo isimli podu en kısa sürede silme
```
kubectl delete pod foo –now
```
***
#### foo isimli podu silmeye zorla
```
kubectl delete pod foo --force
```
