

# btx-miner

Discord: https://discord.gg/aDJwPb3rW

Github: https://github.com/pearlfortune/btx-miner


# Get Started

> ##### ⚠️ V100 users: Please use btx-miner-cu12. Do not choose the miner based on your installed CUDA version (even if CUDA 13 is installed, you should still use btx-miner-cu12).



## Environment Variables

| Command-line argument | Environment variable | Default                    |
| --------------------- | -------------------- | -------------------------- |
| `-payout`             | `BTX_PAYOUT`         | Required in Stratum mode   |
| `-worker`             | `BTX_WORKER`         | `default`                  |
| `-pool`               | `BTX_STRATUM_POOL`   | `global.btxpool.org:23333` |

Explicit command-line values override their environment-variable defaults.


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
                "url": "global.btxpool.org:23333",
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
    -pool stratum+tls://maozi.uk:8665

## CUDA 13
./btx-worker-v4-cu12 \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool stratum+tls://maozi.uk:8665

```
