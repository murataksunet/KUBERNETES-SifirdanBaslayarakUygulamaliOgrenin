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

### nginx image'ini yaml dosyası şeklinde çıktı alın ve text.txt dosyasina aktarına

<details><summary>show</summary>
<p>

```bash
kubectl get po nginx -o yaml >>text.txt
```

</p>
</details>
