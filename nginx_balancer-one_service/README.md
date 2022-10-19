# Implement Nginx load balancer in GKE

This is an update of this tutorial. In especific the ingress because in networking.k8s.io/v1 is necesary an IngressClass
https://www.cloudskillsboost.google/focuses/872?parent=catalog

# Step 1
```
kubectl create deployment hello-app --image=gcr.io/google-samples/hello-app:1.0
```

# Step 2

```
kubectl expose deployment hello-app  --port=8080
```

# Step 3
Add a Chart of ingress-nginx (develop by kubernetes). In this repo you can find more information about the update.
https://github.com/kubernetes/ingress-nginx/blob/main/docs/index.md

**Note:** You can define a new namespace, for example: ingress-nginx



# Step 4

```
kubectl get all -n ingress-nginx

kubectl get service <NGINX_CONTROLLER_NAME> -n ingress-nginx
```

# Step 5

```
kubectl apply -f ingress-resource-update.yaml
```

# Step 6
You can see your web in http://external-ip-of-ingress-controller/hello

**Note:** You can find more information of this update in 

https://docs.konghq.com/kubernetes-ingress-controller/latest/concepts/ingress-versions/
https://kubernetes.io/docs/concepts/services-networking/ingress/
