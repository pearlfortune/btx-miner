

# btx-miner

http://43.154.101.226:8088/btx-pool



**矿池分配模式更新：PPLNS（2000 Share 窗口）**

当前矿池采用 PPLNS 结算模式，窗口大小为 **2000 shares**。
 奖励将基于最近 2000 个有效 share 进行分配，越早提交的 share 权重逐步衰减。



- 最低支付金额：1 BTX
- 支付周期：1小时





# Get Started

## HiveOS

```json
{
    "isFavorite": false,
    "items": [
        {
            "coin": "BTX",
            "pool_ssl": false,
            "dpool_ssl": false,
            "miner": "custom",
            "miner_alt": "btx",
            "miner_config": {
                "url": "global.btxpool.org:23333",
                "miner": "btx",
                "template": "%WAL%",
                "install_url": "https://github.com/pearlfortune/btx-miner/releases/download/v1.18/btx-1.18.tar.gz"
            },
            "pool_geo": []
        }
    ]
}
```



## Linux

```sh
## 下载解压
rm btx-1.18.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v1.18/btx-1.18.tar.gz
tar vxzf btx-1.18.tar.gz

## CUDA 12
cd btx
./btx-miner-cu12 \
    -mode stratum \
    -backend cuda \
    -gpu-devices all \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool global.btxpool.org:23333

## CUDA 13
cd btx
./btx-miner-cu13 \
    -mode stratum \
    -backend cuda \
    -gpu-devices all \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool global.btxpool.org:23333
```





