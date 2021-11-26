# Kubernetes Pod(Declarative) - YAML - Bölüm Alıştırması - 4

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

