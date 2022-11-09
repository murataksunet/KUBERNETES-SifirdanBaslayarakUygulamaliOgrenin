## 🧑 Ders: Imperative Yöntemle POD Yönetimi

### 📗Bu bölümde "kubectl config" komut kullanımını bulacaksınız📗(murataksu.net)

#### kubeconfig dosya yolu
***
```
kubectl config dosyası $HOME/.kube/ yolundaki config isimli dosyadır

Ör: Linux ve Mac /home/murataksunet/.kube/config | Windows C:\Users\maksum\.kube\config
```
#### kubeconfig dosya içeriğini görüntüleme
***
```
kubectl config view
```
***
#### Kubeconfig dosyasında tanımlı context bilgilerini listeleme
```
kubectl config get-contexts
```
***
#### Kubeconfig dosyasında tanımlı cluster bilgilerini listeleme
```
kubectl config get-clusters
```
***
#### Kubeconfig dosyasında tanımlı context bilgisini kullanma
```
kubectl config use-context context-name
```
***
#### Kubeconfig dosyasında tanımlı varsayılan context bilgisini görüntüleme
```
kubectl config current-context
```
***
#### Kubeconfig dosyasında kullanılmayan context tanımı silme
```
kubectl config delete-context my-unused-context
```
***
#### Kubeconfig dosyasında kullanılmayan cluster tanımı silme
```
kubectl config delete-cluster my-old-cluster
```
***
#### Yeni cluster bağlantısı oluşturma
```
kubectl config set-cluster my-cluster --server=127.0.0.1:8087
```
***
#### Cluster için sertifika bilgilerini güncelleme
```
kubectl config set-cluster e2e --certificate-authority=~/.kube/e2e/kubernetes.ca.crt
```
#### e2e cluster için  sertifika denetimini devre dışı bırakma
```
kubectl config set-cluster e2e --insecure-skip-tls-verify=true
```
***
#### Diğer değerlere dokunmadan kullanıcı tanımını değiştirme
```
kubectl config set-context gce --user=cluster-admin
```
***
#### Diğer değerlere dokunmadan kullanıcı kimlik bilgileirni güncelleme
```
kubectl config set-credentials cluster-admin --client-key=~/.kube/admin.key
```
***
#### Cluster-admin kullanıcı bilgilerini tanımlama
```
kubectl config set-credentials cluster-admin --username=admin --password=uXFGweU9l35qcif
```
