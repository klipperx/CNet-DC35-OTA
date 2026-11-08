# CNet-DC35-OTA

Signed firmware updates for the DC35 CNet round badge.

Badges fetch:

- [`manifest.json`](manifest.json)
- [`manifest.json.sig`](manifest.json.sig)

The signature is ECDSA P-256 over SHA-256 of the exact `manifest.json` bytes.
The matching public key is baked into the firmware (`badge/ota_pubkey.h`).
The private key is not in this repository.

Published from the `OTA-Updater` branch of the badge repo with:

```bash
python3 tools/ota_release.py \
  --base-url https://klipperx.github.io/CNet-DC35-OTA \
  --build badge=dist/firmware/badge.ino.bin
```
