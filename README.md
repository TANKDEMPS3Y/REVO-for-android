# REVO 2.1.10 — Android

REVO is a local Xray client: it runs the official Xray core on your device and
connects only to the servers you add. Servers, subscriptions and settings stay on
the phone.

## Files

| File | Purpose |
| --- | --- |
| `REVO-2.1.10-release.apk` | Install this on a phone. Release build, permanently signed with the REVO release key. |
| `REVO-2.1.10-release.aab` | App bundle for uploading to Google Play. Not installable directly. |
| `SHA256SUMS.txt` | SHA-256 checksums of both files. |

## Requirements

- Android 7.0 (API 24) or newer.
- Internet access for the VPN/proxy connection and for subscription updates.

## Install (first time)

1. Copy `REVO-2.1.10-release.apk` to the phone.
2. Open it and allow installing from this source when Android asks.
3. Open REVO, add a server (share link, manual entry, or subscription URL), select
   it and press Connect.
4. Android asks once for VPN permission. REVO needs it for VPN mode; Local proxy
   mode does not.

## Upgrade from an earlier version

This is the **first REVO Android build signed with the permanent release key**.
APKs signed with a different key cannot be installed over each other, so Android
will reject this APK with a signature mismatch on phones that have one of the
earlier debug-key-signed builds (2.1.9 and the initial 2.1.10 build).

- Coming from a **Play build signed with this same permanent key**, install over
  the old version normally; data is kept.
- Coming from a **debug-key-signed build**, there is no in-place upgrade. Android
  requires uninstalling the old app first, and uninstalling removes REVO's local
  data (servers, subscriptions, settings, DNS profiles). Export anything you need
  before uninstalling if the app offers an export for it.
- Later 2.1.x builds signed with this same key will upgrade in place over this
  APK and keep data.

The application ID (`com.revo.android`) is unchanged.

## Verify the download

```sh
sha256sum -c SHA256SUMS.txt
```

The APK's signing certificate SHA-256 fingerprint is:

```
D0:02:63:5D:3C:37:73:17:14:FE:3B:9F:1C:C9:69:49:29:21:DD:77:84:F7:01:D5:3E:EF:FA:D4:FE:71:A5:99
```

## What is new in 2.1.10

- DNS controls are now in **Advanced settings** in one place and one order:
  **Enable Local DNS**, **Enable Fake DNS**, **VPN DNS**.
- **VPN DNS** is the resolver handed to the VPN interface and to the core's
  resolver, so queries stay inside the tunnel. A connected DNS Changer profile
  takes precedence while it is active.
- The connection confirmation vibration now fires from the VPN service on the
  real transition to Connected, using Android's touch vibration channel and the
  system amplitude. Verification updates and reconnects cannot repeat it.
- Version 2.1.10 (versionCode 22000).

See `RELEASE-NOTES-2.1.10.md` for the full list and known limitations.

## Notes

- **Signing:** permanent REVO release key, certificate `CN=REVO, OU=Software,
  O=REVO`, RSA 2048, SHA-256 fingerprint as above. The keystore lives outside this
  project, is not included in this folder, and its passwords are stored only in
  the builder's user-level Gradle properties. Keep the keystore and passwords:
  every future update must be signed with this same key.
- The Xray core is bundled in the APK; its licence is included in the app assets.
- This folder contains no signing keys, keystores, passwords or personal data.

## Licence

The project's `package.json` declares MIT, but this release folder does not
contain a `LICENSE` file because the repository has none. Add the project's
actual licence before publishing if you intend the release to be open source.
