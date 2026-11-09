# changes
⚠️ Compared with the original project's `main` branch, the following changes are required:
- Modify the `config.toml` configuration file:
  ```md
  [Twitter]
  enabled = true
  build-mode = "both"   # 'both', 'apk' or 'module'. default: apk
  patches-source = "crimera/piko-newx"
  patches-version = "v3.75.0"   # 'latest', 'dev', or a version number. default: "latest"
  rv-brand = "Piko"
  # archive-dlurl = "https://archive.org/download/jhc-apks/apks/com.twitter.android"
  archive-dlurl = "xxxxxxxx"
  version = "12.41.0-prod.01"   # 'auto', 'experimental', 'latest' or a version number (e.g. '17.40.41'). default: auto
  included-patches = "'NewX: Restore Twitter branding'"
  enable-update-checks = true
  ```
- Add other applications:`enabled = false`
- Disable automatic execution of GitHub Actions.
  - Modify the file at this path:`.github/workflows/ci.yml`
  ```yaml
  name: CI
  on:
  workflow_dispatch:
  # schedule:      # Disable automatic builds in GitHub Actions
  #   - cron: "0 16 * * *"
  ```

# Related Projects
* [Morphe Patches](https://github.com/MorpheApp/morphe-patches)
* [piko](https://github.com/crimera/piko)
* [piko-newx](https://github.com/crimera/piko-newx)
* [De-Vanced](https://github.com/RookieEnough/De-Vanced)

# Resource Download
* [X(Twitter)-APKMirror](https://www.apkmirror.com/apk/x-corp/twitter/)
  - 11.81.0-release.0 (311810000)
  - 12.22.0-prod.01 (312220001) ✅
  - 12.23.1-prod.01 (312231001)
  - 12.24.0-prod.02 (312240002)
* [Instagram-APKMirror](https://www.apkmirror.com/apk/instagram/instagram-instagram/)
* [jhc-apks-archive](https://archive.org/download/jhc-apks/apks/)

# ReVanced Magisk Module
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/rvc_magisk)
[![CI](https://github.com/j-hc/revanced-magisk-module/actions/workflows/ci.yml/badge.svg?event=schedule)](https://github.com/j-hc/revanced-magisk-module/actions/workflows/ci.yml)

Extensive ReVanced builder  

Get the [latest CI release](https://github.com/j-hc/revanced-magisk-module/releases).

Use [**zygisk-detach**](https://github.com/j-hc/zygisk-detach) to detach YouTube and YT Music from Play Store if you are using magisk modules. 

<details><summary><big>Features</big></summary>
<ul>
 <li> Supports all present and future ReVanced apps (including projects implementing the same API)</li>
 <li> Can build Magisk modules and non-root APKs</li>
 <li> Updated daily with the latest versions of apps and patches</li>
 <li> Optimizes APKs and modules for size</li>
 <li> Modules</li>
    <ul>
     <li> recompile invalidated odex for faster usage</li>
     <li> receive updates from Magisk app</li>
     <li> do not break safetynet or trigger root detections</li>
     <li> handle installation of the correct version of the stock app and all that</li>
     <li> support Magisk and KernelSU</li>
    </ul>
</ul>
</details>

## To include/exclude patches or patch other apps

 * Star the repo :eyes:
 * Use the repo as a [template](https://github.com/new?template_name=revanced-magisk-module&template_owner=j-hc)
 * Customize [`config.toml`](./config.toml) using [rvmm-config-gen](https://j-hc.github.io/rvmm-config-gen/)
 * Run the build [workflow](../../actions/workflows/build.yml)
 * Grab your modules and APKs from [releases](../../releases)

also see here [`CONFIG.md`](./CONFIG.md)

## If you are having trouble with the classic mount method of the modules
such as,
- **"Reflash needed"** error after reboots
- **"Suspicious mount detected"** warnings from root detector apps

You can consider using [rvmm-zygisk-mount](https://github.com/j-hc/rvmm-zygisk-mount)

## Building Locally
### On Termux
```console
bash <(curl -sSf https://raw.githubusercontent.com/j-hc/revanced-magisk-module/main/build-termux.sh)
```

### On Linux
```console
$ git clone https://github.com/j-hc/revanced-magisk-module --depth 1
$ cd revanced-magisk-module
$ ./build.sh
```
