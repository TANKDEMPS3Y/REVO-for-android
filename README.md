# REVO 2.1.10 — Android

REVO is a native Android connectivity application powered by the bundled Xray core. It connects to the servers you add and provides server management, subscription support, and configurable DNS options.

## Download

| File | Purpose |
|---|---|
| `REVO-2.1.10-release-signed.apk` | Official Android installer. Signed with the permanent REVO release key. |
| `SHA256SUMS.txt` | SHA-256 checksum for verifying the APK download. |

## Requirements

- Android 7.0 (API 24) or newer.
- Supported architectures: `arm64-v8a` and `x86_64`.
- 32-bit-only ARM devices are not supported.
- Internet access for VPN/proxy connections and subscription updates.

## Install (First Time)

1. Download `REVO-2.1.10.apk`.
2. Open the APK and allow installation from this source when Android asks.
3. Open REVO and add a server using a share link, manual entry, or subscription URL.
4. Select a server and press Connect.
5. Android requests VPN permission when VPN mode is first activated. Local Proxy mode does not require VPN permission.

## Upgrade from an Earlier Version

This is the first REVO Android release signed with the permanent release key.

APKs signed with a different key cannot be installed over one another.

- If you have an earlier debug-key-signed build (such as 2.1.9 or the initial 2.1.10 build), you must uninstall it before installing this release.
- Uninstalling removes local app data, including servers, subscriptions, settings, and DNS profiles. Back up important configurations first.
- Future REVO 2.1.x releases signed with the same permanent key can be installed over this version while preserving app data.

The application ID remains unchanged: `com.revo.android`.

## Verify the Download

On Windows PowerShell:

```powershell
Get-FileHash .\REVO-2.1.10-release-signed.apk -Algorithm SHA256
```

On Linux or macOS:

```sh
sha256sum -c SHA256SUMS.txt
```

Compare the result with the published SHA-256 checksum.

### Signing Certificate

The APK is signed with the permanent REVO release key.

Certificate SHA-256 fingerprint:

```text
D0:02:63:5D:3C:37:73:17:14:FE:3B:9F:1C:C9:69:49:29:21:DD:77:84:F7:01:D5:3E:EF:FA:D4:FE:71:A5:99
```

## What's New in 2.1.10

- DNS settings have been reorganized under Advanced Settings.
- Local DNS, Fake DNS, and VPN DNS options are now grouped together.
- VPN DNS configures the resolver used by the VPN interface and the Xray core.
- An active DNS Changer profile takes precedence while connected.
- Version: 2.1.10
- Version code: 22000

## Security and Privacy

- The Xray core is bundled with the application.
- The permanent signing keystore and passwords are not included in this repository.
- Always download REVO from this official repository.

## License

REVO is proprietary, closed-source software. Its application source code is not distributed through this repository.

---

Thank you for using REVO!
