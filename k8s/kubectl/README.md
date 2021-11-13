## kubectl install

```
snap install kubectl --classic
```

> version の更新頻度が多いアプリケーション

## kubectl alias setting

```
alias k=kubectl
```

## kubectl basic command

```
kubectl apply -f filename.yml
kubectl get pods [-o wide]
kubectl get deploy
```

```
curl -sfL https://get.k3s.io | sh -s - --docker

curl -sfL https://get.k3s.io | sh -s - "--docker --write-kubeconfig-mode 644"
```

## sudo

```
sudo cat /etc/systemd/system/k3s.service.env
```

```
K3S_USER='nxyt-1'
K3S_KUBECONFIG_MODE="644"
```

```
ls -l  $(which kubectl)
```

```
sudo chown -R $USER ~/.kube
```

```
sudo kubectl config view
```
