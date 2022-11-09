## 🧑 Ders: Affinity

### 📗Bu bölümde Affinity Yönetim işlemlerini bulacaksınız📗(murataksu.net)

#### Nedir ?
***
```
Affinity, Nodeselector yerine daha karmaşık ifadeler yazarak podları dilediğimiz nodelar üzerine yönlendirmenin bir diğer yoludur. 
```
#### Affinity Türleri
***
```
  Node - Pod Affinity / Anti-Affinity
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
#### Örn: POD'u Linux işletim sistemli node üzerine yönlendirme - Zorunlu
```
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - linux
```
***
#### Örn: POD'u Linux işletim sistemlerinden -Ubuntu veya Centos - node üzerine yönlendirme - Tercih
```
  affinity:
    nodeAffinity:
      preferredDuringSchedulingIgnoredDuringExecution:
      - weight: 1
        preference:
          matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - ubuntu
      - weight: 50
        preference:
          matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - centos
```
***
#### Örn: POD'u security=S1 etiketine sahip olan bir zone içerisinde oluşturma - Zorunluluk 
```
  affinity:
    podAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
      - labelSelector:
          matchExpressions:
          - key: security
            operator: In
            values:
            - S1
        topologyKey: topology.kubernetes.io/zone
```
***
#### Örn: POD'u security=S2 etiketine sahip OLMAYAN bir hostname içerisinde oluşturma - Tercih 
```
    podAntiAffinity:
      preferredDuringSchedulingIgnoredDuringExecution:
      - weight: 100
        podAffinityTerm:
          labelSelector:
            matchExpressions:
            - key: security
              operator: In
              values:
              - S2
          topologyKey: topology.kubernetes.io/hostname
```
