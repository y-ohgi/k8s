
# helm
```console
$ brew install kubernetes-helm
$ kubectl create serviceaccount tiller --namespace kube-system
$ kubectl create clusterrolebinding tiller --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
$ helm init --upgrade --service-account tiller
```

```console
$ kubectl apply -f ./serviceaccount.yaml
$ helm init --upgrade --service-account tiller
```

