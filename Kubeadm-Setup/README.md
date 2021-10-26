
***********************************************************************************************************************************************
.
. Demo:  "Kubeadm" ile Kubernetes Kurulumu  |  Murat AKSU
.

***********************************************************************************************************************************************

# 1. 3 VM - master(1) ve worker(2) nodes Olacak Şekilde Kurulum Yapıyoruz

Donanım İhtiyacı
----------------------------------------------------
Master: 1 vCPUs - 4GB Ram  
Worker: 2 vCPUs - 3GB RAM
OS:     CentOS/RHEL 7

NOT: Aşağıdaki adımlar ilgili node üzerinde çalıştırılacaktır
***********************************************************************************************************************************************

# Master Node Üzerinde
hostnamectl set-hostname master-node

# Worker Node 1 Üzerinde
hostnamectl set-hostname worker-node-1

# Worker Node 2 Üzerinde
hostnamectl set-hostname worker-node-2


NOT: Aşağıdaki adımlar hem master hemde worker nodelar üzerinde çalıştırılacaktır
***********************************************************************************************************************************************
# 2. IP Adreslerin Sabitlenmesi.Kendi IP adresinize göre düzenleyin
# Tüm Nodelar Üzerinde
cat <<EOF>> /etc/hosts
192.168.100.120 master-node
192.168.100.121 worker-node-1
192.168.100.122 worker-node-2
EOF

NOT: Aşağıdaki adımlar hem master hemde worker nodelar üzerinde çalıştırılacaktır
***********************************************************************************************************************************************

# 3.  Firewall | Swap | SELinux Kapatma

# SELinux Pasif Et
setenforce 0
sed -i --follow-symlinks 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux

#Sistem Yeniden Başlatılacak
reboot

# Swap Pasif Et
swapoff -a
sed -i.bak -r 's/(.+ swap .+)/#\1/' /etc/fstab


NOT: Aşağıdaki adımlar hem master hemde worker nodelar üzerinde çalıştırılacaktır
***********************************************************************************************************************************************

# Kubernetes Repository tanımla
cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
exclude=kube*
EOF


# Sistem güncelleme ve Docker | Kubelet | Kubeadm | Kubectl Kurulum
yum update -y
yum install -y docker kubeadm kubelet kubectl --disableexcludes=kubernetes


# Docker ve Kubectl aktif etme ve başlatma
systemctl enable docker && systemctl start docker
systemctl enable kubelet && systemctl start kubelet

/////////////////////////////////////////////////////////////////

NOT: Aşağıdaki adımlar sadece master node üzerinde yapılacak

/////////////////////////////////////////////////////////////////

***********************************************************************************************************************************************

# 5. Kubernetes "master" node yapılandırma

kubeadm init

---------------------------------------------------------------------

# kubectl standart user konfigurasyonu
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config



/////////////////////////////////////////////////////////////////

NOT: Aşağıdaki adımlar sadece worke nodelar üzerinde yapılacak

/////////////////////////////////////////////////////////////////


************************************************************************************************************************************************

# 6. "worker" nodeların kubernetes clustera eklenemesi. Sizde ki üretilen çıktıya göre ekleme işlemi yapılacak

#  Master Node yapılandırması tamamlandıktan sonra üretilen komut worker nodelar üzerinde çalıştırılacaktır

kubeadm join 192.168.100.120:6443 --token tv17b1.dlsj9vbl8pc42pr1 \
        --discovery-token-ca-cert-hash sha256:1a58dc3bb7904e3d3508498cf26a0064b2b1180e6629c473375deebff251eebf


NOT: Aşağıdaki adımlar Master node üzerinde çalıştırılacaktır
***********************************************************************************************************************************************
# 7. Pod Network Yapılandırma

export kubever=$(kubectl version | base64 | tr -d '\n')
kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$kubever"

************************************************************************************************************************************************

# 8. Test

# Nodeları Görüntüle
kubectl version --short

# Oluşturulan Pod'u Görüntüleme
kubectl get po -o wide


************************************************************************************************************************************************
