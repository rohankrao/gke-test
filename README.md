# Kubernetes helm chart for IZAC


## Configure helm

```
kubectl -n kube-system create serviceaccount tiller
kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller
```

## Install IZAC helm charts

```
helm install --name izac izac-helm-charts
kubectl get pods
kubectl get svc
```


## Managing the release

```
helm del --purge izac
helm ls
```

## Managing pods

```
kubectl describe pod <pod-name>
kubectl logs --follow <pod-name>
```

## Managing GKE cluster

```
gcloud compute firewall-rules create myservice --allow tcp:30000-32767
gcloud compute instances list
gcloud container clusters resize standard-cluster-1 --num-nodes=1 --zone us-central1-a
```

## Setting up NGINX-Ingress

```
# Install ingress controller
helm install --name nginx-ingress stable/nginx-ingress --set rbac.create=true

# Save the below text and change service name, host and path
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  annotations:
    kubernetes.io/ingress.class: nginx
  name: ingress
spec:
  rules:
    - host: www.example.com
      http:
        paths:
          - backend:
              serviceName: exampleService
              servicePort: 80
            path: /

# Then apply the file
kubectl apply -f <ingress-file>.yml
```