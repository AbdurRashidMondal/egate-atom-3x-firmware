# 🔧 Flash from an SD card or USB drive

> Uses the `aml_sdc_burn.ini` script shipped with the package. **Erases the bootloader and flash.** Generic Amlogic method, **not verified** on this model.

## 🚨 What the script does

| Setting | Value | Meaning |
|---|---|---|
| `erase_bootloader` | `1` | Bootloader is erased and rewritten |
| `erase_flash` | `1` | All data is wiped |
| `reboot` | `1` | Device restarts when done |
| `package` | `aml_upgrade_package.img` | File name the tool looks for |

## 📋 Prerequisites

| Item | Detail |
|---|---|
| Card | SD card or USB drive formatted FAT32 |
| Files | `aml_sdc_burn.ini` and `aml_upgrade_package.img` in the **root** of the card |
| Image | Checksum verified before copying |
| Power | Mains power the whole time |

## 🔧 Steps

| # | Action | Expected result |
|---|---|---|
| 1 | Format the card FAT32 | Empty card |
| 2 | Copy both files to the root | Two files visible |
| 3 | Insert the card into the powered-off projector | Card seated |
| 4 | Power on with the recovery or reset button held | Flash screen or progress bar |
| 5 | Wait until it restarts | Device boots normally |

> ⚠️ TODO: this model's trigger button is not confirmed. The device may ignore the card unless its bootloader supports card burning.
