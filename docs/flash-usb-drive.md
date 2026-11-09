# 🔧 PRIMARY METHOD: flash from a USB pendrive

> The main way to install this firmware on the E GATE Atom 3X, using a USB pendrive and the projector's power button. **Erases all data.** Method supplied by the projector's owner; steps are reported, not independently re-tested.

## ⚡ Quick path

```mermaid
flowchart LR
    A[Copy files to pendrive] --> B[Plug pendrive into projector]
    B --> C[Power on projector]
    C --> D[Picture appears]
    D --> E[Immediately press and HOLD Power button]
    E --> F[Screen shows Updating...]
    F --> G[Wait until it restarts]
```

## 📋 Prerequisites

| Item | Detail |
|---|---|
| Pendrive | USB pendrive, formatted **FAT32** (image is 2.08 GiB, under FAT32's 4 GiB file limit) |
| Free space | At least 3 GB |
| Files | **All** files from the firmware package (see below), in the **root** of the pendrive |
| Download | `aml_upgrade_package.img.7z` from the [Release](https://github.com/AbdurRashidMondal/egate-atom-3x-firmware/releases/tag/v1.0.0), SHA256 verified |
| Extract | `7z x aml_upgrade_package.img.7z` gives `aml_upgrade_package.img`, MD5 verified |
| Power | Projector on mains power the whole time |

## 📦 Files to copy to the pendrive root

| File | Required | Purpose |
|---|---|---|
| `aml_upgrade_package.img` | ✅ | The firmware, **extracted from the `.7z`** (do not copy the `.7z` itself) |
| `aml_sdc_burn.ini` | ✅ | Burn script (`erase_bootloader=1`, `erase_flash=1`, `reboot=1`) |
| `md5.txt` | optional | Checksum shipped with the package |

> Copy the files directly to the root. **Not** inside a folder.

## 🔧 Steps

| # | Action | Expected result |
|---|---|---|
| 1 | Extract the `.7z`, then copy all the package files into the pendrive root | Files visible at the top level |
| 2 | Plug the pendrive into the projector's USB port | Drive seated |
| 3 | Turn on the projector | Boot picture appears |
| 4 | **As soon as the picture appears, press and hold the Power button again** | Keep holding |
| 5 | Keep holding **until the screen shows "Updating..."** | Update screen appears |
| 6 | Release and wait. Do not unplug power or the pendrive | Progress completes, projector restarts |
| 7 | Let the first boot finish (several minutes) | System starts normally |

## 🚨 Rules while updating

| Do | Do not |
|---|---|
| Keep mains power connected | Unplug power during "Updating..." |
| Leave the pendrive in until it restarts | Remove the pendrive early |
| Wait for the first boot | Power off because it seems slow |

## 🐛 If "Updating..." does not appear

| Symptom | Try |
|---|---|
| Normal boot or boot loop continues | Repeat from step 3, press and hold Power **earlier**, right when the picture appears |
| Drive ignored | Try a different pendrive and another projector USB port |
| Files not found | Confirm both files are in the root and names are unchanged |
| Still failing | Use the PC route: [flash-usb-burning-tool.md](flash-usb-burning-tool.md) |

## 🔄 After the update

1. Wait for the first boot to complete.
2. Do a factory reset from Settings if the system misbehaves.
3. Remove the pendrive and turn off USB / Network / Wireless debugging if you enabled it.
