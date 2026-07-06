

# btx-miner

Website: https://btx.pearlfortune.org

Website: https://btxpool.org/

Discord: https://discord.gg/aDJwPb3rW

Github: https://github.com/pearlfortune/btx-miner


# Get Started

## Servers
```text
global.btxpool.org:23333
global.pearlfortune.org:23333
```

## Other Config Arguments

- `CORE_CUDA_BLOCKING_SYNC=1` - Reduces CPU usage during mining. May slightly reduce hashrate.

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
                "install_url": "https://github.com/pearlfortune/btx-miner/releases/download/v2.7.0/btx-v2.7.0.tar.gz"
            },
            "pool_geo": []
        }
    ]
}
```



## Linux

```sh
## Dowaload
rm -f btx-v2.7.0.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v2.7.0/btx-v2.7.0.tar.gz
tar vxzf btx-v2.7.0.tar.gz

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

## NVIDIA V100
cd btx
./btx-miner-cu12 \
    -mode stratum \
    -backend cuda \
    -gpu-devices all \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool global.btxpool.org:23333
```



