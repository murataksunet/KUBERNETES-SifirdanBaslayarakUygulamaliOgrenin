# Kubernetes Pod(Imperative) - CLI- Hadi Başlıyalım

## Lütfen aşagıdaki alıştırmalari demo sisteminizde cevaplandiriniz

### Windows veya linux uzerinde kubernetes config dosyasina ulasin

<details><summary>show</summary>
<p>

```bash
$HOME/.kube/config # Linux
C:\Users\maksum\.kube #Windows
```

</p>
</details>

### Kubernetes cluster üzerinde ki config dosyasını görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl config view
```

</p>
</details>

### Aktif olan config dosyasini görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl config current-context 
```

</p>
</details>

### docker-desktop  konfigin kullanilmasini saglayan komutunu yazin

<details><summary>show</summary>
<p>

```bash
*kubectl config use-context <docker-desktop>
```

</p>
</details>

### Windows üzerinde kubectl'i k kısayolu haline getirin

<details><summary>show</summary>
<p>

```bash
Set-Alias -Name k -Value kubectl 
#Veya
Set-Alias -Name k -Value C:\K8S-Tools\kubectl.exe
```

</p>
</details>

### Kubernetes cluster durumunu kontrol edin

<details><summary>show</summary>
<p>

```bash
kubectl cluster-info 
```

</p>
</details>

### Kubernetes versiyon bilgisini görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl version
```

</p>
</details>


### Kubernetes uzerinde ki nodelari ipleri ile listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl get nodes -o wide
```

</p>
</details>

### Control plane node uzerinde allocated resources detaylarini goruntuleyin

<details><summary>show</summary>
<p>

```bash
kubectl describe node <node ismi>
```

</p>
</details>


### Kubernetes uzerinde ki namespaceleri goruntuleyin

<details><summary>show</summary>
<p>

```bash
kubectl get namespace
```

</p>
</details>


### Kubernete uzerinde tum namespacelerde calisan podlari listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl get pods --all-namespaces 
```

</p>
</details>


### Clusterdaki tum namespacelerde calisan nesneleri listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl get all --all-namespaces 
```

</p>
</details>


### Pod nesnesinin manifest detaylarini goruntuleyin

<details><summary>show</summary>
<p>

```bash
kubectl explain pod
```

</p>
</details>
