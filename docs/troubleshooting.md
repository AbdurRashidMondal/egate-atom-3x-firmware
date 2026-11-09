# 🐛 Troubleshooting and boot-loop notes

> One E GATE Atom 3X got stuck on the boot animation after a debloat session. This page records what was changed so others can avoid it. **The cause is suspected, not proven.**

## 🚨 What was disabled before the boot loop

The apps were disabled with `pm disable-user --user 0 <package>`, then the projector was restarted and never finished booting.

| Package | Role |
|---|---|
| `com.jixin.analytics` | Vendor telemetry |
| `com.jixin.apppush` | Vendor app suggestions |
| `com.jixin.ota` | Vendor system update |
| `com.android.printspooler` | Printing |
| `com.android.htmlviewer` | HTML viewer |
| `com.android.wallpaperbackup` | Backup helper |
| `com.android.sharedstoragebackup` | Backup helper |
| `com.android.backupconfirm` | Backup helper |
| `com.android.localtransport` | Backup helper |
| `com.android.adservices.api` | Android ad services |
| `com.android.ondevicepersonalization.services` | Android personalization |
| `com.android.sdksandbox` | Android SDK sandbox |
| `com.android.nearby.halfsheet` | Nearby sharing |
| `com.android.companiondevicemanager` | Companion devices |

Also changed: `jLauncher5ShowApps` (launcher app list) and the three animation scales set to `0`.

## ❌ Do not disable on this board

| Package | Reason |
|---|---|
| `com.jixin.launcher5` | Only home screen. Without it there is nothing to boot into |
| `com.jixin.dispatcher`, `com.define.shellservice` | Vendor services, likely needed |
| `com.droidlogic*` | Amlogic framework (display, keystone, TV input) |
| `com.google.android.gms`, `com.android.vending` | Google services |
| `com.android.systemui`, settings apps | Core UI |

## 🔄 If it is already stuck

| Step | Action |
|---|---|
| 1 | Try recovery and a factory reset (clears disabled-app state, erases data) |
| 2 | If that fails, reflash with the firmware from `aml_upgrade_package.img.7z` (extract it first) using the guides in this folder |
| 3 | Do not repeat the debloat. Disable only apps that were proven safe |

> ⚠️ TODO: record here which of the 14 packages actually caused the loop, if someone tests them one at a time on a recoverable unit.
