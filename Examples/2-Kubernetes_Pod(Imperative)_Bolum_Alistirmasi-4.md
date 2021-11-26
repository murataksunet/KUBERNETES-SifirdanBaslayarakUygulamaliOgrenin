# Kubernetes Pod(Imperative) - Hadi Başlıyalım - Bölüm Alıştırması - 4

#### nginx1,nginx2,nginx3 adlarıyla 3 adet pod oluşturun. Hepsine app=production label ekleyin.

<details><summary>show</summary>
<p>

```bash
kubectl run nginx1 --image=nginx --restart=Never --labels=app=production
kubectl run nginx2 --image=nginx --restart=Never --labels=app=production
kubectl run nginx3 --image=nginx --restart=Never --labels=app=production
```

</p>
</details>

#### JSON formatını kullanarak tüm podlari lisleteyin(araştır)

<details><summary>show</summary>
<p>

```bash
kubectl get pods -o=jsonpath="{.items[*]['metadata.name']}"
```

</p>
</details>


#### JSON formatını kullarak 1.podun ismini name değişkenine aktarın ve görüntüleyin

<details><summary>show</summary>
<p>

```bash
$name=kubectl get pods -o=jsonpath="{.items[1]['metadata.name']}"
echo $name
```

</p>
</details>

#### Yaml dosyasi oluturma. busybox image'ını kullanan vaybe adinda bir pod oluşturun. Pod içerisinde sonraki komutunu çalıştırın. Çıktıyı vaybe.yaml dosyasına aktarın.Görünüleyin"while true; do echo "$(date) | $(du -sh ~)" >> /var/logs/diskspace.txt; sleep 5; done;"

<details><summary>show</summary>
<p>

```bash
kubectl run vaybe --image=busybox --restart=Never -o yaml --dry-run -- /bin/sh -c 'while true; do echo "$(date) | $(du -sh ~)" >> /var/logs/diskspace.txt; sleep 5; done;' > vaybe.yaml
cat vaybe.yaml
```

</p>
</details>

#### Tüm namespacelerde bulunan podlardaki label'ları listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl get nodes --show-labels --all-namespaces
```

</p>
</details>

#### Node'lar üzerindeki label'ları listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl get pods --show-labels
```

</p>
</details>


#### nginx2 podunun label'ını app=demo olarak etiketleyin

<details><summary>show</summary>
<p>

```bash
kubectl label po nginx2 app=demo --overwrite
```

</p>
</details>


#### app etiketine sahip podları listeleyin

<details><summary>show</summary>
<p>

```bash
kubectl get po -L app
```

</p>
</details>

#### app=demo olan podu listeleyin.Her iki yazım şeklinide kullanın

<details><summary>show</summary>
<p>

```bash
kubectl get po -l app=demo
# or
kubectl get po -l 'app in (demo)'
```

</p>
</details>

#### app label'ına sahip podlardaki app etiketini kaldırın (araştır)

<details><summary>show</summary>
<p>

```bash
kubectl label po nginx1 nginx2 nginx3 app-
# veya
kubectl label po nginx{1..3} app-
```

</p>
</details>

#### Tüm podlar'a status=healty etiketini ekleyin

<details><summary>show</summary>
<p>

```bash
kubectl label pods --all status=healthy
```

</p>
</details>


#### nginx1 Podunu editleyin ve team=dev etiketini ekleyin. Podu detaylandırına bakıp etiketi görün

<details><summary>show</summary>
<p>

```bash
kubectl run busybox --image=busybox --command --restart=Never -- env
kubectl logs busybox
```

</p>
</details>

#### status=healty olan env!=demo podları listeleyin.Her iki yazım şekliyle yazın

<details><summary>show</summary>
<p>

```bash
kubectl get po -l "status=healty,env!=demo"
#veya
kubectl get po -l "status in (healty),env notin (demo)"
```

</p>
</details>

#### env=production olan labela sahip podları silin

<details><summary>show</summary>
<p>

```bash
kubectl delete pods -l "env=production"
```

</p>
</details>

#### node ismi alomerkez olan node'a disktype=ssd etiketi ekleyin. Görüntüleyin

<details><summary>show</summary>
<p>

```bash
kubectl label nodes alomerkez disktype=ssd
kubectl describe node alomerkez
#veya
kubectl get nodes --show-labels
```

</p>
</details>


#### alomerkez node üzerine eklediğiniz disktype=ssd etiketi kaldırın

<details><summary>show</summary>
<p>

```bash
kubectl label node alomerkez disktype-
```

</p>
</details>
