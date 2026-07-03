

# btx-miner

Website: https://btx.pearlfortune.org


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
## Dowaload
rm -f btx-1.18.tar.gz
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





