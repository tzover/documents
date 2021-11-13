# Local 環境での k3s 環境構築方法

```
curl -sfL https://get.k3s.io | sh -s - --docker --write-kubeconfig-mode 644
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
```

- KUBECONFIG は下記でも OK

```
sudo cp  /etc/rancher/k3s/k3s.yaml /home/nxyt-2/.kube
export KUBECONFIG=/home/nxyt-2/.kube
```

- k3sup を使ってインストールする場合は kubeconfig ファイルが生成されるのでそこの PATH を KUBECONFIIG に通す

```
export KUBECONFIG=/home/nxyt-2/k3s/kubeconfig
```
