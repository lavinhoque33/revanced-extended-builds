<div align="center">

  # ReVanced Extended builds (lavinhoque33)

  [![CI](https://github.com/lavinhoque33/revanced-extended-builds/actions/workflows/ci.yml/badge.svg?event=schedule)](https://github.com/lavinhoque33/revanced-extended-builds/actions/workflows/ci.yml)
  [![Release date](https://img.shields.io/github/release-date/lavinhoque33/revanced-extended-builds)](https://github.com/lavinhoque33/revanced-extended-builds/releases)
  [![Release version](https://img.shields.io/github/v/release/lavinhoque33/revanced-extended-builds?display_name=release)](https://github.com/lavinhoque33/revanced-extended-builds/releases/latest)
  [![License](https://img.shields.io/github/license/lavinhoque33/revanced-extended-builds)](LICENSE)
</div>

---

Prebuilt YouTube and YouTube Music with [lavinhoque33's ReVanced Extended patches](https://github.com/lavinhoque33/revanced-patches). Those patches are a fork of [anddea's patches](https://github.com/anddea/revanced-patches) with support for newer app versions and extra patches, such as **Restore Android Auto playlists**.

Every build is published as a numbered release under [Releases](https://github.com/lavinhoque33/revanced-extended-builds/releases):

| File | For |
|---|---|
| `youtube-revanced-extended-v<version>-arm64-v8a.apk`<br>`youtube-music-revanced-extended-v<version>-<arch>.apk` | Non-root: install like a normal app. It installs next to the original app under its own package name. Needs [MicroG-RE](https://github.com/MorpheApp/MicroG-RE) for Google sign-in. |
| `youtube-revanced-extended-module-v<version>-arm64-v8a.zip`<br>`youtube-music-revanced-extended-module-v<version>-<arch>.zip` | Root: flash in Magisk or KernelSU. The module installs the matching stock app and mounts the patched one over it. |

`<arch>` is `arm64-v8a` (almost every phone) or `arm-v7a` (old 32-bit phones). The `stock` release only holds unmodified build inputs that GitHub's runners cannot download from APKMirror.

**Signing:** every APK is signed with this repository's own key, which is kept in repository secrets. Before installing, you can check that the certificate's SHA-256 is
`5F:91:55:46:4D:9D:FA:EA:02:DE:80:8C:22:0B:82:9C:00:DB:E9:9F:93:17:A8:AE:E7:1E:F7:98:F8:05:D7:7F`
(for example with `apksigner verify --print-certs <file>.apk`, or the App Manager app). Build No. 1 used the builder's public default key: if you installed a non-root APK from it, uninstall it before installing a newer build.

## 📌 Configuration

| | YouTube RVX | YouTube Music RVX |
|---|---|---|
| App version | 21.39.525 (arm64-v8a, Android 12L+) | 9.40.51 (arm64-v8a and armeabi-v7a) |
| Extra included patches | Visual preferences icons for YouTube, Return YouTube Username | Visual preferences icons for YouTube Music, Return YouTube Username, Disable music video in album |
| Excluded patches | Custom header for YouTube | Custom header for YouTube Music |
| App name | YouTube RVX | YT Music RVX |
| App icon | [Vanced Black](https://github.com/anddea/revanced-patches/wiki/Icons) | [Vanced Black](https://github.com/anddea/revanced-patches/wiki/Icons) |
| Light theme background | #FFF9F9F9 | – |

Settings are in [`config.toml`](config.toml); see [CONFIG.md](CONFIG.md) for every option.

## 🔄 Updates

- CI checks every hour. It builds when a new release of the [patches fork](https://github.com/lavinhoque33/revanced-patches/releases) is out or when that release supports a newer app version.
- Magisk modules update from the Magisk app (they point at this repository's `update` branch).
- Root: use [zygisk-detach](https://github.com/j-hc/zygisk-detach) so the Play Store does not replace the patched apps.

## 🙏 Credits

- [j-hc](https://github.com/j-hc) for the [ReVanced Magisk module builder](https://github.com/j-hc/revanced-magisk-module) and [zygisk-detach](https://github.com/j-hc/zygisk-detach)
- [ev3rlin](https://github.com/ev3rlin) for the [ReVanced Extended version](https://github.com/ev3rlin/ReVanced-Extended) of the builder this repository is forked from
- [anddea](https://github.com/anddea) for the [ReVanced Extended patches](https://github.com/anddea/revanced-patches)
- [Morphe](https://github.com/MorpheApp) for Morphe CLI and [MicroG-RE](https://github.com/MorpheApp/MicroG-RE)
