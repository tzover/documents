## k3sup (ケチャップ) install

- single node

```
k3sup install --ip $MASTER_IP --user $K3S_USER --k3s-extra-args "--docker --write-kubeconfig-mode 644"
```

- multi node

```
k3sup install --ip $MASTER_IP --user $K3S_USER --k3s-extra-args "--docker --with-node-id --node-label $LABEL1=$LABEL_NAME_M1 --node-taint CriticalAddonsOnly=true:NoExecute --node-taint node-role.kubernetes.io/master=true:NoSchedule --write-kubeconfig-mode 644"
```
