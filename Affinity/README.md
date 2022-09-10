## 🧑 Ders: Affinity

### 📗Bu bölümde Affinity Yönetim işlemlerini bulacaksınız📗

#### Nedir ?
***
```
Affinity, Nodeselector yerine daha karmaşık ifadeler yazarak podları dilediğimiz nodelar üzerine yönlendirmenin bir diğer yoludur. 
```
#### Affinity Türleri
***
```
  Node Affinity
  Node Anti-Affinity
```
***
#### Seçim İşlemi
```
Zorunluluk:
requiredDuringSchedulingIgnoredDuringExecution
Tercih:
preferredDuringSchedulingIgnoredDuringExecution
```
***
#### Node üzerinde standart eklenen label bilgileri
```
kubernetes.io/hostname
failure-domain.beta.kubernetes.io/zone
failure-domain.beta.kubernetes.io/region
beta.kubernetes.io/instance-type
beta.kubernetes.io/os
beta.kubernetes.io/arch

```
***
#### POD'un talep edilen node üzerinde oluşturulduğunun kontrolü
```
kubectl get pods -o wide
```
