# 機器同士を local 環境で SSH する方法

---

## 機器同士を優先 LAN ケーブルで接続

- Jetson を想定

## 1 台目

### WiFi の設定を OFF にする

- System Settings -> Network -> Wireless -> OFF

### IPv6 の設定を ignore に変更する

- System Settings -> Network -> Wired -> options -> IPv6 Settings -> Method -> Automatic -> ignore

### IPv4 の設定を manual に変更する (IP は任意)

- System Settings -> Network -> Wired -> options -> IPv6 Settings -> Method -> Automatic(DHCP) -> manual

- Additional static addresses -> Add

  |   Address   | Netmask |   Gateway   |
  | :---------: | :-----: | :---------: |
  | 172.168.0.2 |   24    | 172.168.0.1 |

## 2 台目

### WiFi の設定を OFF にする

- System Settings -> Network -> Wireless -> OFF

### IPv6 の設定を ignore に変更する

- System Settings -> Network -> Wired -> options -> IPv6 Settings -> Method -> Automatic -> ignore

### IPv4 の設定を manual に変更する (IP は任意)

- System Settings -> Network -> Wired -> options -> IPv6 Settings -> Method -> Automatic(DHCP) -> manual

- Additional static addresses -> Add

  |   Address   | Netmask |   Gateway   |
  | :---------: | :-----: | :---------: |
  | 172.168.0.3 |   24    | 172.168.0.1 |

## SSH 接続する ( 1 -> 2 に接続 )

```
ssh ${hostname}@172.168.0.3

-> password を入力
```
