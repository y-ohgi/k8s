k8s
---

# About this repository
GKEの備忘録

# Commands
## initial
```console
$ export PROJECT_NAME=<YOUR PROJECT NAME>
$ gcloud init
$ gcloud config set project $PROJECT_NAME
$ gcloud auth login
$ gcloud set compute/zone asia-northeast1-a
$ gcloud components install kubectl
```

## create cluster
プリエンプティブインスタンスで起動する

```console
$ gcloud beta container clusters create "sample-cluster" \
    --zone "asia-northeast1-a" \
    --preemptible --num-nodes "3" \
    --cluster-version "1.9.6-gke.1"\
    --machine-type "n1-standard-1"
$ gcloud container clusters get-credentials sample-cluster --zone=asia-northeast1-a
```

```conosle
$ gcloud container clusters delete sample-cluster
```


# tools
* [jonmosco/kube-ps1](https://github.com/jonmosco/kube-ps1)
* [ahmetb/kubectx](https://github.com/ahmetb/kubectx)
* [wercker/stern](https://github.com/wercker/stern)

