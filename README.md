

# btx-miner

Website: https://btx.pearlfortune.org

Website: https://btxpool.org/

Discord: https://discord.gg/aDJwPb3rW

Github: https://github.com/pearlfortune/btx-miner


# Get Started

> ##### ⚠️ V100 users: Please use btx-miner-cu12. Do not choose the miner based on your installed CUDA version (even if CUDA 13 is installed, you should still use btx-miner-cu12).

## Servers
```text
global.btxpool.org:23333
```

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
./btx-miner-cu12 \
    -mode stratum \
    -backend cuda \
    -gpu-devices all \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool global.btxpool.org:23333

## CUDA 13
./btx-miner-cu13 \
    -mode stratum \
    -backend cuda \
    -gpu-devices all \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool global.btxpool.org:23333

## NVIDIA V100
## ⚠️ V100 users: Please use btx-miner-cu12.
## Do not choose the miner based on your installed CUDA version (even if CUDA 13 is installed, you should still use btx-miner-cu12).
./btx-miner-cu12 \
    -mode stratum \
    -backend cuda \
    -gpu-devices all \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -pool global.btxpool.org:23333
```

## Linux (AMD)
```sh
## Dowaload
rm -f btx-amd-v2.9.2.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v2.9.2/btx-amd-v2.9.2.tar.gz
tar vxzf btx-amd-v2.9.2.tar.gz
cd btx-amd

## Start
./btxminer-rocm \
  -mode stratum \
  -backend rocm \
  -gpu-devices all \
  -payout your-btx-wallet-address \
  -worker "$(hostname)" \
  -pool global.btxpool.org:23333
```

## MacOS
```sh
## Dowaload
rm -f btxminer-metal-hardened-v6-v2.9.3.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v2.9.3/btxminer-metal-hardened-v6-v2.9.3.tar.gz
tar vxzf btxminer-metal-hardened-v6-v2.9.3.tar.gz

## Start
./btxminer-metal-hardened-v6 \
    -mode stratum \
    -backend metal \
    -pool global.btxpool.org:23333 \
    -payout your-btx-wallet-address \
    -worker "$(hostname)" \
    -log-interval 10s
```

## SRB miner

https://github.com/doktor83/SRBMiner-Multi/releases

```json
{
    "isFavorite": false,
    "items": [
        {
            "coin": "BTX",
            "pool_ssl": false,
            "dpool_ssl": false,
            "miner": "srbminer_custom",
            "miner_config": {
                "url": "global.btxpool.org:23333",
                "algo": "btx",
                "miner": "srbminer_custom",
                "template": "%WAL%.%WORKER_NAME%",
                "install_url": "https://github.com/doktor83/SRBMiner-Multi/releases/download/3.4.6/srbminer_custom-3.4.6.tar.gz"
                "user_config": "--disable-cpu"
            },
            "pool_geo": []
        }
    ]
}
```
