### 📗Bu bölümde Kubeadm Kurulum adımlarını bulacaksınız📗

#### 3 VM - master(1) ve worker(2) nodes Olacak Şekilde Kurulum Yapıyoruz
***
```
Donanım İhtiyacı

Master: 1 vCPUs - 4GB Ram
Worker: 2 vCPUs - 3GB RAM OS: CentOS/RHEL 7
```
***
#### Hostname değişikliği yap. Aşağıdaki adımlar ilgili node üzerinde çalıştırılacaktır
```
Master Node Üzerinde hostnamectl set-hostname master-node
Worker Node 1 Üzerinde hostnamectl set-hostname worker-node-1
Worker Node 2 Üzerinde hostnamectl set-hostname worker-node-2
```
***
#### Aşağıdaki adımlar hem master hemde worker nodelar üzerinde çalıştırılacaktır
```
2. IP Adreslerini IP bloğunuza  göre düzenleyin
Tüm Nodelar Üzerinde
cat <> /etc/hosts 192.168.100.120 master-node 192.168.100.121 worker-node-1 192.168.100.122 worker-node-2 EOF
```
***
### NOT: Aşağıdaki adımlar hem master hemde worker nodelar üzerinde  çalıştırılacaktır
```
minikube start
```
***
#### Nodeları listele
```
kubectl get nodes
```
***
#### Minikube web arayüzünü aç
```
minikube dashboard
```
