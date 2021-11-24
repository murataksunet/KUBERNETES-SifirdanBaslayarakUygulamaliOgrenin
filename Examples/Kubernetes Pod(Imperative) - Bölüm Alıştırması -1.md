# Minikube

## Lütfen aşağıdaki alıştırmayı sırasıyla yapınız!

### minikube durum bilgisini görüntüleyin

<details><summary>show</summary>
<p>

```bash
minikube status
```

</p>
</details>

### minikube üzerindeki lokal cluster'ı silin

<details><summary>show</summary>
<p>

```bash
minikube delete
```

</p>
</details>

### minikube üzerinde yeni bir lokal cluster oluşturun
<details><summary>show</summary>
<p>

```bash
minikube start
```

</p>
</details>

### minikube üzerinde control plane ve worker node ekleyin (araştır). Tüm node Ip'lerini listeleyin.
<details><summary>show</summary>
<p>

```bash
minikube node add --control-plane
minikube node add --worker
minikube ip
```

</p>
</details>

### minikube üzerinde node listelemesi yapın ve silin
<details><summary>show</summary>
<p>

```bash
minikube node list
minikube node delete
```

</p>
</details>

### minikube üzerinde control plane ve worker node ekleyin (araştır)
<details><summary>show</summary>
<p>

```bash
minikube node add --control-plane
minikube node add --worker
```

</p>
</details>


