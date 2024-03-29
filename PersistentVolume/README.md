## 🧑 Ders: Persistent Volume

### 📗Bu bölümde Persistent Volume ve Persistent Volume Claim Yönetim işlemlerini bulacaksınız📗(murataksu.net)

#### Persistent Volume
***
```
Persistent Volume, kubernetes cluster içerisinde herhangi bir node’a bağlı olmayan, kalıcı veri depolama alanını tanımlamak için 
kullandığımız nesnedir. Farklı veri depolama türlerini desteklemektedir.
```
***
#### Persistent Volume Clam
```
Pod için talep edilen kapasiteyi PV üzerinden tanımlayan nesnedir. Pod -> PVC -> PV -> Storage
```
***
#### Desteklenen PersistentVolume Türleri
```
cephfs - CephFS volume
csi - Container Storage Interface (CSI)
fc - Fibre Channel (FC) storage
hostPath - HostPath volume (for single node testing only; WILL NOT WORK in a multi-node cluster; consider using local volume instead)
iscsi - iSCSI (SCSI over IP) storage
local - local storage devices mounted on nodes.
nfs - Network File System (NFS) storage
rbd - Rados Block Device (RBD) volume
```
***
#### Tüm persistentvolume leri listele
```
kubectl get persistentvolume
```
***
#### Tüm persistentvolumeclaim leri listele
```
kubectl get persistentvolumeclaim
```
***
#### mypv-volume isimli persistentvolume nesnesini listele
```
kubectl get pv mypv-volume
```
***
#### mypvc-volume isimli persistentvolumeclaim nesnesini listele
```
kubectl get pvc mypvc-volume
```
***
#### pvc-volume isimli persistentvolumeclaim nesnesi detaylarını görüntüle
```
kubectl describe pvc pvc-volume
```
***
#### pv-volume isimli persistentvolume nesnesini detaylarını görüntüle
```
kubectl describe pv pv-volume
```
***
#### Tanımlı tüm Storage Class nesnelerini görüntüle
```
kubectl get storageclass
```
***
#### Tanımlı Storage Class nesnesi detaylarını görüntüle
```
kubectl describe sc
```
***
#### pv-volume isimli persistentvolume nesnesini sil
```
kubectl delete pv pv-volume 
```
***
#### pvc-volume isimli persistentvolumeclaim nesnesini sil
```
kubectl delete pvc pvc-volume 
```
