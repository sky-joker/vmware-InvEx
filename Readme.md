# vmware-InvEx

![](https://github.com/sky-joker/vmware-get-perfcounter-info/blob/master/img/output_image.png)

vCenter上のESXiホストと仮想マシンの情報を取得してExcel(xlsx)に出力するツール

## 必要条件

* python3
* pyvmomi
* openpyxl

## サポート

* vCenter 6.0以上

## インストール

```bash
git clone https://github.com/sky-joker/vmware-InvEx.git
cd vmware-InvEx
pip3 install -r requirements.txt
chmod +x vmware-InvEx.py
```

## 使い方

```bash
$ ./vmware-InvEx -vc vcenter.local
$ ls output.xlsx
output.xls
```

## 取得できる情報

### ESXi

| 項目               | 説明                                                   |
|:-------------------|:-------------------------------------------------------|
| HostName           | ESXiのホスト名                                         |
| Vendor             | サーバのベンダー                                       |
| Model              | サーバのモデル                                         |
| uuid               | vCenterが識別で使用しているESXiのuuid                  |
| BIOS Version       | BISOバージョン                                         |
| CPU Hz             | CPUの周波数                                            |
| CPU Socket         | CPUのソケット数                                        |
| CPU Core           | CPUのコア数                                            |
| CPU Thread         | CPUのスレッド数                                        |
| CPU HyperThread    | ハイパースレッドの有無(有効:TRUE/無効:False)           |
| Memory Size        | サーバのメモリー容量                                   |
| ESXi Version       | ESXiのバージョン                                       |
| ESXi Build Version | ESXiのビルドバージョン                                 |
| ESXi Cluster       | ESXiが所属してるクラスタ名                             |
| ESXi Datastore     | ESXiがマウントしているデータストア(カンマ区切りで出力) |
| ESXi VM            | ESXi上に存在するVM数                                   |
| ESXi ManageIP      | ESXi管理IP                                             |
| ESXi SubnetMask    | ESXi管理IPのサブネットマスク                           |
| ESXi MacAddress    | ESXi管理IPが設定されているNICのMacAddress              |
| ESXi ManagePG      | ESXi管理IPのポートグループ                             |
| ESXi DefaultGW     | ESXi管理IPのデフォルトゲートウェイ                     |
| ESXi DNS           | ESXiに設定されているDNS                                |

### VirtualMachine

| 項目                 | 説明                                                                 |
|:---------------------|:---------------------------------------------------------------------|
| HostName             | 仮想マシンの仮想マシン名                                             |
| InstanceUuid         | vCenterが識別で使用している仮想マシンのInstanceUuid                  |
| ResourcePool         | 仮想マシンが所属しているクラスタ or ESXiホスト                       |
| VMwareTools Status   | VMwareToolsのステータス                                              |
| VMwareTools Version  | VMwareToolsのバージョン                                              |
| OS                   | 仮想マシンのOSタイプ                                                 |
| CPU Socket           | CPUのソケット数                                                      |
| CPU Core             | CPUのコア数                                                          |
| CPU Reservation      | CPUの予約                                                            |
| CPU Limit            | CPUの制限                                                            |
| Memory Size          | 仮想マシンのメモリー容量                                             |
| Memory Reservation   | Memoryの予約                                                         |
| Memory Limit         | Memoryの制限                                                         |
| CDROM                | CD/DVDのマウント情報(存在しない場合は空)                             |
| Floppy               | Floppyのマウント情報(存在しない場合は空)                             |
| USB                  | USBのマウント情報(存在しない場合は空)                                |
| Disk Total Size      | 仮想マシンのvmdk合計容量                                             |
| IPAddress            | 仮想マシンに設定されているIPアドレス(VMwareToolsから取得)            |
| Network Adapter N PG | 仮想マシンのネットワークアダプターの接続先ポートグループ情報(最大10) |

## ライセンス

[MIT](https://github.com/sky-joker/vmware-InvEx/blob/master/LICENSE.txt)

## 作者

[sky-joker](https://github.com/sky-joker)
