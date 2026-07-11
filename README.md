

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

## Other Config Arguments

- `CORE_CUDA_BLOCKING_SYNC=1` - Reduces CPU usage during mining. May slightly reduce hashrate.

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
                "install_url": "https://github.com/pearlfortune/btx-miner/releases/download/v2.9.3/btx-v2.9.3.tar.gz"
            },
            "pool_geo": []
        }
    ]
}
```



## Linux (NVIDIA)

```sh
## Dowaload
rm -f btx-v2.9.3.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v2.9.3/btx-v2.9.3.tar.gz
tar vxzf btx-v2.9.3.tar.gz
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
rm -f btx-amd-v2.9.3.tar.gz
wget -c https://github.com/pearlfortune/btx-miner/releases/download/v2.9.3/btx-amd-v2.9.3.tar.gz
tar vxzf btx-amd-v2.9.3.tar.gz
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

# BTX Miner 2.9.2 Power Consumption & Hashrate Preview

Snapshot time: `2026-07-10T20:28:06+08:00`  
Network hashrate: `356 MH/s`  
Filter: `worker_version = 2.9.2`

Note: GPU hashrate may fluctuate depending on the total network hashrate, network difficulty, and share calculation window. The following data is collected from currently online miners running **BTX Miner 2.9.2** under the above network hashrate snapshot.

---

## NVIDIA CMP 50HX

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 50-100 W | 201 | 92.3 W | 3.01 kH/s |
| 100-150 W | 10685 | 128.5 W | 3.74 kH/s |
| 150-200 W | 1273 | 165.5 W | 4.22 kH/s |
| 200-250 W | 83 | 210.9 W | 4.35 kH/s |

## NVIDIA CMP 30HX

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 50-100 W | 3137 | 65.7 W | 1.58 kH/s |

## NVIDIA GeForce RTX 3070

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 50-100 W | 292 | 91.2 W | 3.14 kH/s |
| 100-150 W | 1202 | 116.7 W | 3.51 kH/s |
| 150-200 W | 115 | 173.9 W | 3.85 kH/s |

## NVIDIA CMP 40HX

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 50-100 W | 837 | 71.8 W | 1.76 kH/s |
| 100-150 W | 116 | 105.8 W | 2.11 kH/s |

## NVIDIA CMP 90HX

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 100-150 W | 88 | 134.9 W | 2.83 kH/s |
| 150-200 W | 409 | 171.3 W | 3.57 kH/s |

## NVIDIA GeForce RTX 5060

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 50-100 W | 361 | 77.4 W | 3.45 kH/s |

## Tesla V100-SXM2-32GB

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 250-300 W | 274 | 268.3 W | 4.98 kH/s |

## NVIDIA GeForce RTX 4070 SUPER

| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| 100-150 W | 136 | 136.5 W | 4.94 kH/s |
| 150-200 W | 123 | 168.2 W | 6.13 kH/s |
| 200-250 W | 247 | 216.8 W | 6.66 kH/s |

## MacOS M3 Ultra
| Power Range | Samples | Avg Power | Avg Hashrate |
|---:|---:|---:|---:|
| - W | - | - W | 2.1 kH/s |
