### 📗Bu bölümde Kubeadm Kurulum adımlarını bulacaksınız📗

#### 3 VM - master(1) ve worker(2) nodes Olacak Şekilde Kurulum Yapıyoruz
***
```
Donanım İhtiyacı

Master: 1 vCPUs - 4GB Ram
Worker: 2 vCPUs - 3GB RAM 
OS: CentOS/RHEL 7
```
***
#### Host dosyası üzerinde Hostname tanımlaması yapıyoruz. Aşağıdaki adımlar ilgili node üzerinde çalıştırılacaktır
```
#set-hostname master-node //Master Node Üzerinde hostnamectl 
#set-hostname worker-node-1 //Worker Node 1 Üzerinde hostnamectl 
#set-hostname worker-node-2 //Worker Node 2 Üzerinde hostnamectl 
```
***
#### /etc/hosts içerisine node ip bilgilerini ekliyoruz
```
Tüm Nodelar Üzerinde çalıştırılacak (IP Adreslerini IP bloğunuza göre düzenleyiniz)
cat <> /etc/hosts 192.168.100.120 master-node 192.168.100.121 worker-node-1 192.168.100.122 worker-node-2 EOF
```
***
### NOT: Aşağıdaki adımlar hem master hemde worker nodelar üzerinde  çalıştırılacaktır
***
####  Firewall | Swap | SELinux Kapatma
```
SELinux Pasif Ediyoruz
setenforce 0 sed -i --follow-symlinks 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux

#Sistemi Yeniden Başlatıyoruz

Swap Pasif Ediyoruz
swapoff -a sed -i.bak -r 's/(.+ swap .+)/#\1/' /etc/fstab
```
***
#### Kubernetes Repository tanımlıyoruz
```
cat < /etc/yum.repos.d/kubernetes.repo [kubernetes] name=Kubernetes baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64 enabled=1 gpgcheck=1 repo_gpgcheck=1 gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg exclude=kube* EOF
```
***
#### Sistem güncelleme ve Docker | Kubelet | Kubeadm | Kubectl Kurulumu yapıyoruz
```
yum update -y yum install -y docker kubeadm kubelet kubectl --disableexcludes=kubernetes
```
***
#### Docker ve Kubectl aktif edip başlatıyoruz
```
systemctl enable docker && systemctl start docker systemctl enable kubelet && systemctl start kubelet
```
***
### Aşağıdaki adımlar sadece master node üzerinde yapılacak
***
#### Kubernetes "master" node yapılandırma
```
kubeadm init
```
***
#### kubectl standart user konfigurasyonu
```
mkdir -p $HOME/.kube sudo cp -i /etc/kubernetes/admin.conf
$HOME/.kube/config sudo chown $(id -u):$(id -g) $HOME/.kube/config
```
***
### Aşağıdaki adımlar sadece worke nodelar üzerinde yapılacak
***
#### "worker" nodeların kubernetes clustera eklenmesi. Sizde ki üretilen çıktıya göre ekleme işlemi yapılacaktır 
####  Master Node yapılandırması tamamlandıktan sonra üretilen komut worker nodelar üzerinde çalıştırılacaktır
```
kubeadm join 192.168.100.120:6443 --token tv17b1.dlsj9vbl8pc42pr1
--discovery-token-ca-cert-hash sha256:1a58dc3bb7904e3d3508498cf26a0064b2b1180e6629c473375deebff251eebf
```
***
### Aşağıdaki adımlar Master node üzerinde çalıştırılacaktır
***
#### Pod Network Yapılandırma
```
export kubever=$(kubectl version | base64 | tr -d '\n') kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$kubever"
```
***
#### Test Nodeları Görüntüle
```
kubectl version --short
```
***
#### Oluşturulan Pod'u Görüntüleme
```
kubectl get po -o wide
```
