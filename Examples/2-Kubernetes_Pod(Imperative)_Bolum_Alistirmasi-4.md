# Kubernetes Pod(Imperative) - Hadi Başlıyalım - Bölüm Alıştırması - 4

### nginx1,nginx2,nginx3 adlarıyla 3 adet pod oluşturun. Hepsine app=production label ekleyin.

<details><summary>show</summary>
<p>

```bash
kubectl run nginx1 --image=nginx --restart=Never --labels=app=production
kubectl run nginx2 --image=nginx --restart=Never --labels=app=production
kubectl run nginx3 --image=nginx --restart=Never --labels=app=production
```

</p>
</details>

### JSON formatını kullanarak tüm podlari lisleteyin(araştır)

<details><summary>show</summary>
<p>

```bash
kubectl get pods -o=jsonpath="{.items[*]['metadata.name']}"
```

</p>
</details>


### JSON formatını kullarak 1.podun ismini name değişkenine aktarın ve görüntüleyin

<details><summary>show</summary>
<p>

```bash
$name=kubectl get pods -o=jsonpath="{.items[1]['metadata.name']}"
echo $name
```

</p>
</details>

### Yaml dosyasi oluturma. busybox image'ını kullanan vaybe adinda bir pod oluşturun. Pod içerisinde sonraki komutunu çalıştırın. Çıktıyı vaybe.yaml dosyasına aktarın."while true; do echo "$(date) | $(du -sh ~)" >> /var/logs/diskspace.txt; sleep 5; done;"

<details><summary>show</summary>
<p>

```bash
kubectl run vaybe --image=busybox --restart=Never -o yaml --dry-run -- /bin/sh -c 'while true; do echo "$(date) | $(du -sh ~)" >> /var/logs/diskspace.txt; sleep 5; done;' > vaybe.yaml
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
