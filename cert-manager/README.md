

# cert-manager
## DNS Sevice Account
```console
$ export GCLOUD_PROJECT=$(gcloud config get-value project)
$ gcloud iam service-accounts create cert-manager --display-name "cert-manager"
$ gcloud projects add-iam-policy-binding ${GCLOUD_PROJECT} --member serviceAccount:cert-manager@${GCLOUD_PROJECT}.iam.gserviceaccount.com --role roles/dns.admin
$ gcloud iam service-accounts keys create cert-manager-key.json --iam-account cert-manager@${GCLOUD_PROJECT}.iam.gserviceaccount.com
$ kubectl create secret generic clouddns-service-account --from-file=cert-manager-key.json=cert-manager-key.json -n kube-system
```

## install
```console
$ helm install stable/cert-manager --namespace kube-system
```

## create tls
```console
$ kubectl apply -f ./clusterissuer.yaml
$ kubectl apply -f ./certificate.yaml
```

## deploy
```console
$ kubectl apply -f ./deployment.yaml
$ kubectl apply -f ./ingress.yaml
```
