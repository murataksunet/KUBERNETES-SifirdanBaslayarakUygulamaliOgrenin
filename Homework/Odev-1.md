# Ödev Cevabı
#


```sh
kubectl run ubuntu --image=ubuntu --labels=team=system --env="HEY_SERVICE_HOST=10.10.10.10" --restart=Never --command -- sleep infinity
```

```sh
kubectl exec ubuntu -it -- /bin/bash
apt update
apt install nginx
apt install curl
service nginx restart
curl localhost
```

```sh
echo "Web Sayfama Hosgeldiniz" > index.html
kubectl cp index.html ubuntu:/var/www/html/
```

```sh
kubectl port-forward ubuntu 8080:80
```

```sh
kubectl exec ubuntu -- env
```

```sh
kubectl explain pod.status.hostIP
kubectl get po ubuntu -o=jsonpath='{.status.hostIP}' > podhostip.txt
```

```sh
kubectl label po ubuntu team=developer --overwrite
kubectl label po ubuntu app=webserver 
```

```sh
kubectl delete po -l app=webserver
```

```sh
kubectl run debug --image=busybox --labels=app=debug --env="MYAPP_SERVICE_PORT=443" --restart=Never --dry-run=client -o yaml --command -- sleep infinity > debug.yaml
```
