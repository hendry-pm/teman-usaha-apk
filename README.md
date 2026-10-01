# Teman Usaha — release APKs

Signed Android builds of **Teman Usaha**, a bookkeeping app for older
micro-entrepreneurs in Indonesia. The source lives in a private repository;
only build artifacts are published here.

## Which file

Install **`app-universal-...apk`** if you are not sure. It works on any phone.

The per-ABI files are smaller and are what the app's own updater downloads
once it has asked Android which architecture the handset is:

| file | for |
|---|---|
| `app-arm64-v8a-...apk` | most phones made since about 2017 |
| `app-armeabi-v7a-...apk` | older 32-bit phones |
| `app-universal-...apk` | anything — larger, always works |

There is deliberately no `x86_64` build. That is the emulator's architecture
and has no business on a handset.

## Checking what you downloaded

**Do not trust a checksum published next to a file**, including this one — if
someone could replace the file they could replace the list beside it. The app
takes its checksums from the Teman Usaha server over HTTPS and refuses an
archive that does not match, which is what makes it safe for the bytes
themselves to come from a dumb public host like this one.

To check by hand:

```sh
sha256sum app-universal-release-v0.1.0-b24.apk
```

## Installing

Android will ask whether to allow installing from this source. That prompt is
expected for an app that does not come from the Play Store; allow it once.

**Never uninstall to update.** Installing a newer build over an older one
keeps the shop's records, including anything not yet sent to the server.
Uninstalling deletes them. Every build published here is signed with the same
key, so updating in place always works.
