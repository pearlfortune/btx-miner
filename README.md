

# btx-miner

Discord: https://discord.gg/aDJwPb3rW

Github: https://github.com/pearlfortune/btx-miner


# Get Started


## HiveOS (NVIDIA)

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
                "url": "stratum+tls://btx-hk.lproute.com:8665",
                "miner": "btx",
                "template": "%WAL%",
                "install_url": "https://github.com/pearlfortune/btx-miner/releases/download/v2.11.1/btx-v2.11.1.tar.gz"
            },
            "pool_geo": []
        }
    ]
}
```



## Linux (NVIDIA)

```sh
## Dowaload
rm -f btx-v2.11.1.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v2.11.1/btx-v2.11.1.tar.gz
tar vxzf btx-v2.11.1.tar.gz
cd btx

## CUDA 12
./btx-worker-v4-cu12 \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool stratum+tls://btx-hk.lproute.com:8665

## CUDA 13
./btx-worker-v4-cu12 \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool stratum+tls://btx-hk.lproute.com:8665

```
