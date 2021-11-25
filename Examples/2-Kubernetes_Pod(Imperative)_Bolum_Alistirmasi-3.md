# Kubernetes Pod(Imperative) - Hadi Başlıyalım - Bölüm Alıştırması - 3

### Mariadb imageını kullanan ismi mymariadb olan bir pod oluşturun. Root password bilgisini ekleyin. Restart never şeklinde olacak

<details><summary>show</summary>
<p>

```bash
kubectl run mariadb --image=mariadb --restart=Never --env=MYSQL_ROOT_PASSWORD='Passw0rd!'
```

</p>
</details>

### Komut satırında mymariadb podunun loglarını görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl logs mymariadb 
```

</p>
</details>

### mymariadb poduna giriş yapın. Mariadb database uygulamasına giriş yapıp databaseleri listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl exec -it mymariadb -- mariadb -uroot -p
show databases;
```

</p>
</details>

### mymariadb poduna giriş yapmadan database path'ini listeleyin(/var/lib/mysql/)

<details><summary>show</summary>
<p>

```bash
kubectl exec mymariadb -- ls /var/lib/mysql/
```

</p>
</details>

### Minikube üzerinde dashboard ekranında mymariadb podu loglarına görüntüleyin.

<details><summary>show</summary>
<p>

```bash
minikube dashboard
#Sol bölümden pod sekmesine girip mymariadb erişin ve log sekmesini açın
```

</p>
</details>

### mymariadb databaseine dışarıdan uygulama üzerinden erişmek için port yönlendirme işleminini yapın. Uygulama üzerinden test işlemini yapın

<details><summary>show</summary>
<p>

```bash
kubectl port-forward mymariadb 8080:80
```

</p>
</details>


### busybox image'ını kullanan ve ekrana hello world yazdıran pod oluşturun. İşlem tamamlandığında pod silinsin.

<details><summary>show</summary>
<p>

```bash
kubectl run busybox --image=busybox -it --rm --restart=Never -- /bin/sh -c 'echo hello world'
```

</p>
</details>


### nginx image'ını kullanan yeni bir pod oluşturun. Env bilgisi olarak var=vol1 bilgisini ekleyin

<details><summary>show</summary>
<p>

```bash
kubectl run nginx --image=nginx --restart=Never --env=var1=val1
```

</p>
</details>

### nginx image'ını kullanan yeni bir pod oluşturun. Env bilgisi olarak var=vol1 bilgisini ekleyin. Pod içerisine girmeden env bilgisini listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl run nginx --image=nginx --restart=Never --env=var1=val1
kubectl exec -it nginx -- env
```

</p>
</details>

### nginx image'ini yaml formatı şeklinde text.txt dosyasina aktarına

<details><summary>show</summary>
<p>

```bash
kubectl get po nginx -o yaml >>text.txt
```

</p>
</details>

### Nginx image'ını daha anlaşılır API nesneleri olmadan pod.yaml dosyasina yazdırın (araştır).Görüntüle

<details><summary>show</summary>
<p>

```bash
kubectl run nginx --image=nginx --restart=Never --dry-run -o yaml > pod.yaml
cat pod.yaml
```

</p>
</details>


### env komutunu çalıştıran yeni bir busybox pod oluştur(command komutu kullan(araştır)). Loglarini listele

<details><summary>show</summary>
<p>

```bash
kubectl run busybox --image=busybox --command --restart=Never -- env
kubectl logs busybox
```

</p>
</details>

### env komutunu çalıştıran yeni bir busybox pod oluştur(command komutu kullan). yaml dosyasına API nesneleri olmadan aktar. Görüntüle.

<details><summary>show</summary>
<p>

```bash
kubectl run busybox --image=busybox --restart=Never --dry-run -o yaml --command  -- env > envpod.yaml
cat envpod.yaml
```

</p>
</details>
