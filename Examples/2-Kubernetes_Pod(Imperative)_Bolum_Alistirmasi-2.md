# Kubernetes Pod(Imperative) - Hadi Başlıyalım - Bölüm Alıştırması - 2

## Lütfen aşagıdaki alıştırmalari demo sisteminizde cevaplandiriniz

### myweb adinda nginx image'ını kullanan bir pod oluşturun

<details><summary>show</summary>
<p>

```bash
kubectl run myweb --image=nginx
```

</p>
</details>

### myweb pod'u ip bilgisiyle birlikte görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl get po -o wide
```

</p>
</details>

### myweb pod'un detaylarını görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl describe pod myweb
```

</p>
</details>

### myweb pod'u yaml dosyası olarak görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl get pod myweb -o yaml
```

</p>
</details>

### Tüm pod'ları sadece isim ve namespace olacak şekilde listeleyin (araştır)

<details><summary>show</summary>
<p>

```bash
kubectl get pods -o custom-columns=NAME:.metadata.name,RSRC:.metadata.namespace
```

</p>
</details>

### myweb poduna bağlanmadan date bilgisini alın ve root dizinini listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl exec myweb -- date
```

</p>
</details>

### myweb poduna giriş yapıp root(/) dizininde storage adinda bir folder oluşturun. Bu folder içerisinde password(icine yazin) adinda bir file oluşturun

<details><summary>show</summary>
<p>

```bash
kubectl exec -it myweb -- bash
mkdir storage
cd storage
echo "9sdf908092ad" >>password
```

</p>
</details>


### Pod içerisinde oluşturduğunuz password dosyasını lokal bilgisayarına kopyalayın

<details><summary>show</summary>
<p>

```bash
kubectl cp default/myweb:storage/ .
```

</p>
</details>



### Lokalde index.html adında bir dosya oluşturun. Bu dosyayı myweb podunun yayın yapılan dosyası üzerine kopyalayın

<details><summary>show</summary>
<p>

```bash
kubectl cp index.html myweb:/usr/share/nginx/html/
```

</p>
</details>

### index.html dosyasını cat komutuyla görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl exec  myweb -- cat /usr/share/nginx/html/index.html
```

</p>
</details>


### myweb poduna 8080 port yönlendirme işlemini yapıp sayfanızın gelip gelmediğini test edin

<details><summary>show</summary>
<p>

```bash
kubectl port-forward myweb 8080:80
```

</p>
</details>

### myweb poduna silin

<details><summary>show</summary>
<p>

```bash
kubectl delete pod myweb
```

</p>
</details>
