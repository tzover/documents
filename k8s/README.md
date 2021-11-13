# Kubenetes Practice

## k3sup (ケチャップ) install

- single node

```
k3sup install --ip $MASTER_IP --user $K3S_USER --k3s-extra-args "--docker --write-kubeconfig-mode 644"
```

- multi node

```
k3sup install --ip $MASTER_IP --user $K3S_USER --k3s-extra-args "--docker --with-node-id --node-label $LABEL1=$LABEL_NAME_M1 --node-taint CriticalAddonsOnly=true:NoExecute --node-taint node-role.kubernetes.io/master=true:NoSchedule --write-kubeconfig-mode 644"
```

## home に k3s directory を作る

```
cd ~
mkdir k3s
```

# k3s 利用の前提

> k3s クラスターの構成には以下の３台の Node が必要

- Setup Node
- k3s master Node
- k3s worker Node

## Setup Node の事前準備

1. k3s server agent を実行する Node の IP アドレスを確認
2. k3sup を実行する端末に ssh/config を作成
3. k3sup インストールを実行する端末側に SSH 秘密鍵と公開鍵を作成
4. 作成した公開鍵を k3s server,agent を実行する端末へ転送

### 作業用ディレクトリの作成

```
cd ~
mkdir k3s
```

### IP アドレスの確認

```
ifconfig
```

### 秘密鍵公開鍵の作成

```
cd ~/.ssh
ssh-keygen -t rsa -f ssh-key_id_rsa
```

### k3sup install を実行する端末の ~/.ssh/config に設定を追記する

```
vim ~/.ssh/config
```

Add

```
HOST k3s_master_1
  HostName {マスター端末のIPアドレス}
  User {マスター端末のuser}
  Port 22
  Identityfile ~/.ssh/ssh-key_id_rsa

HOST k3s_worker_1
  HostName {ワーカー端末1のIPアドレス}
  User {ワーカー端末1のuser}
  Port 22
  Identityfile ~/.ssh/ssh-key_id_rsa

HOST k3s_worker_2
  HostName {ワーカー端末2のIPアドレス}
  User {ワーカー端末2のuser}
  Port 22
  Identityfile ~/.ssh/ssh-key_id_rsa
```

export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
