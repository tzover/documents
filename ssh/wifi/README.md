# 機器同士を WiFi 環境で SSH する方法

---

## 機器同士を優先 LAN ケーブルで接続

- Jetson を想定

### WiFi の設定を 確認する

```
ifconfig
```

> wlan0 -> inet 192.168.128.186

## SSH 接続する

```
ssh ${hostname}@192.168.128.186

-> password を入力
```
