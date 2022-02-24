## 🧑 Ders: ConfigMap

### 📗Bu bölümde ConfigMap Nesne Yönetim işlemlerini bulacaksınız📗

#### YAML dosyası hardware limit detayları
***
```
kubectl create configmap empty-config
```
***
#### YAML Hardware detayları
```
kubectl create configmap special-config --from-literal=special.how=very
```
***
#### Pod'un kullandığı CPU-MEMORY kulllanım değerini görüntüleme
```
kubectl create configmap special-config --from-literal=special.how=very --from-literal=special.type=charm
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl create configmap app-settings --from-file=app-container/settings/app.properties
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
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
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl describe configmaps game-config
```
***
#### Tüm namespacelerdeki POD ların cpu-memory kullanım değerlerini görüntüleme
```
kubectl delete configmaps game-config
```
