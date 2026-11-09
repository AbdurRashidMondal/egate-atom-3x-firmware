# 🔧 Flash with Amlogic USB Burning Tool

> **Fallback method.** The primary method is [flash-usb-drive.md](flash-usb-drive.md).
> Writes `aml_upgrade_package.img` from a Windows PC. **Erases all data.** These are the generic Amlogic steps; they have **not** been verified on this model.

## 📋 Prerequisites

| Item | Detail |
|---|---|
| PC | Windows with the Amlogic USB Burning Tool and its driver installed |
| Cable | USB-A to USB-A data cable (a USB-C to A cable did not work in testing) |
| Image | `aml_upgrade_package.img`, checksum verified |
| Power | Projector on mains power the whole time |

## 🔧 Steps

| # | Action | Expected result |
|---|---|---|
| 1 | Open USB Burning Tool, choose **File > Import image**, select the `.img` | Tool shows the image loaded |
| 2 | Leave **Erase flash** and **Reset after success** as the guide describes | Options set |
| 3 | Connect the cable from the PC to the projector's PC-facing USB port | A new Amlogic device appears |
| 4 | Put the projector into burn mode (reset or burn pinhole held while powering on) | Tool lists the device as connected |
| 5 | Click **Start** | Progress bar runs to 100% |
| 6 | Wait for success, then unplug USB and power-cycle | Device boots |

> ⚠️ TODO: the burn-mode button for this model was not confirmed. Ask E-Gate support or record it here once found.

## 🐛 If the PC does not see the device

| Symptom | Try |
|---|---|
| Nothing in Device Manager | Other USB port on the projector, rear PC port, A-to-A cable |
| Unknown device | Reinstall the Burning Tool driver |
| Tool says connected, then fails | Re-check the checksum and cable |

## 🔄 After flashing

1. Let the first boot finish (several minutes).
2. Do a factory reset from Settings if the system misbehaves.
