# 🔍 Device info

> Values read from a working E GATE Atom 3X over ADB before it was changed. Use them to confirm you own the same hardware.

| Property | Value |
|---|---|
| `ro.product.model` | `t950s_be311` |
| `ro.product.device` | `t950s_be311` |
| `ro.product.board` | `ljs5` |
| `ro.hardware` | `amlogic` |
| `ro.build.version.release` | `13` |
| `ro.build.version.sdk` | `33` |
| `ro.build.fingerprint` | `Google/ap201/ap201:13/TQ2A.230405.003.E1/14:userdebug/test-keys` |
| RAM | about 981 MB total |
| Screen | 1920 x 1080 |
| Default launcher | `com.jixin.launcher5` (system app) |

## 🧪 How to check yours

```powershell
adb connect <TV_IP>:<PORT>
adb shell getprop ro.product.board     # expect: ljs5
adb shell getprop ro.product.model     # expect: t950s_be311
```

> The ADB port on this unit was not 5555. `adb mdns services` listed it.

## 🔍 Package match

| Check | Result |
|---|---|
| Image path inside `md5.txt` | `out/target/product/ljs5/aml_upgrade_package.img` |
| Board name on the device | `ljs5` |
| Image header magic | `0x27b51956` (Amlogic) |
