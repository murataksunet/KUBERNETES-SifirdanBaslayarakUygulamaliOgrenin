# Minikube

## Lütfen aşağıdaki alıştırmayı demo ortamınızda sırasıyla uygulayınız

### 1- minikube durum bilgisini görüntüleyin

<details><summary>show</summary>
<p>

```bash
minikube status
```

</p>
</details>

### 2- minikube üzerindeki lokal cluster'ı silin

<details><summary>show</summary>
<p>

```bash
minikube delete
```

</p>
</details>

### 3- minikube üzerinde yeni bir lokal cluster oluşturun. Veya 2 node'lu bir cluster kurun. 
<details><summary>show</summary>
<p>

```bash
minikube start
#veya
minikube start --nodes 2 -p multinode-demo
```

</p>
</details>

### 4- Cluster'a control plane veya worker node olarak ekleyin (araştır). 
<details><summary>show</summary>
<p>

```bash
minikube node add --control-plane
#veya
minikube node add --worker
```

</p>
</details>


### Tüm node Ip'lerini listeleyin.
<details><summary>show</summary>
<p>

```bash
minikube ip
```

</p>
</details>

### 5- minikube üzerinde node listelemesi yapın ve silin
<details><summary>show</summary>
<p>

```bash
minikube node list
minikube node delete <node isim>
```

</p>
</details>

### 6- minikube kaynaklarına (sanal makinasına-VM) login olun 
<details><summary>show</summary>
<p>

```bash
minikube ssh
```

</p>
</details>

### 7- minikube üzerindeki Kubernetes dashboard ekranına erişin
<details><summary>show</summary>
<p>

```bash
minikube dashboard
```

</p>
</details>


### 8- minikube üzerindeki imagelari listeleyin
<details><summary>show</summary>
<p>

```bash
minikube image ls
```

</p>
</details>


### 9- minikube üzerine python image'ını indirin ve silin
<details><summary>show</summary>
<p>

```bash
minikube image pull python
minikube image rm image python
```

</p>
</details>


### 10- minikube üzerine lokalde cachede bulunan imageları listele, yenide yükle ve sil 
<details><summary>show</summary>
<p>

```bash
minikube cache list
minikube cache reload
minikube cache delete 
```

</p>
</details>

Daha fazlası: https://minikube.sigs.k8s.io/docs/commands/
