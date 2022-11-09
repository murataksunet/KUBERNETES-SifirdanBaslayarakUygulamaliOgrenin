## 🧑 Ders: Label-Selector

### 📗Bu bölümde Label-Selector kullanarak Pod Yönetim işlemlerini bulacaksınız📗(murataksu.net)

***
#### Equality-based requirement
```
environment = production
tier != frontend
```
***
#### Set-based requirement
```
environment in (production, qa)
tier notin (frontend, backend)
```
***
#### Pod'a Label atama
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version="9.0" 
```
***
#### Node'a Label atama
```
kubectl label nodes node1 disktype=ssd
```
***
#### Bir namespace’deki tüm objelere toplu halde label atama
```
kubectl label pods --all foo=bar
```
***
#### Node üzerinde ki Label bilgisini kaldırma
```
kubectl label node minikube kubernetes.io/say-
```
***
#### Pod üzerindeki label bilgisini kaldırma
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version-
```
***
#### Label olan Pod üzerinde değişiklik yapma
```
kubectl label pod tomcat-labelpod-2 app.kubernetes.io/version="10.0" --overwrite
```
#### Podlara atanan labelları listeleme
***
```
kubectl get po --show-labels
```
***
#### Pod üzerinde bulunan labelları görüntüleme
```
kubectl describe pod tomcat-labelpod-1
```
#### Selector kullanarak Label üzerinden POD listeleme 
***
```
kubectl get po -l app.kubernetes.io/version="8.0" -o wide
```
***
#### Selector kullanarak Label üzerinden POD Silme
```
kubectl delete po -l app.kubernetes.io/name=tomcat
```
***
#### Selector kullanarak Label üzerinden POD Listeleme
```
kubectl get pods -l "app=prod,tier=frontend" --show-labels
```
***
#### Selector kullanarak Label üzerinden POD Listeleme
```
kubectl get pods -l 'app in (prodapp)' --show-labels
```
***
#### Selector kullanarak Label üzerinden POD Listeleme
```
kubectl get pods -l 'app in (prodapp,demoapp)' --show-labels
```
***
#### Selector kullanarak Label üzerinden POD Listeleme
```
kubectl get pods -l 'app in (prodapp),tier notin (frontend)' --show-labels
```
***
#### Selector kullanarak Label üzerinden POD Listeleme
```
kubectl get pods -l 'app notin prodapp)' --show-labels
```
