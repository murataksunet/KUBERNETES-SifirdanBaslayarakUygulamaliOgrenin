## 🧑 Ders: ConfigMap

### 📗Bu bölümde ConfigMap Nesne Yönetim işlemlerini bulacaksınız📗

#### Boş ConfigMap Nesnesi Oluşturma
***
```
kubectl create configmap empty-config
```
***
#### ConfigMap Nesnesi Oluşturma
```
kubectl create configmap special-config --from-literal=special.how=very
```
***
#### ConfigMap Nesnesi Oluşturma
```
kubectl create configmap special-config --from-literal=special.how=very --from-literal=special.type=charm
```
***
#### ConfigMap Nesnesi Oluşturma
```
kubectl create configmap app-settings --from-file=app-container/settings/app.properties
```
***
#### YAML üzerinden ConfigMap Nesnesi Oluşturma
```
apiVersion: v1
kind: ConfigMap
metadata:
  name: game-demo
data:
  player_initial_lives: "3"
  ui_properties_file_name: "user-interface.properties"
```
***
#### ConfigMap Nesnesi Detaylarını Görüntüleme
```
kubectl describe configmaps game-config
```
***
#### ConfigMap Nesnesi Silme
```
kubectl delete configmaps game-config
```
