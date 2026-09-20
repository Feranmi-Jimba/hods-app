# HODS

Turn a document into a colour code you can print, send or scan — and turn it
back into the original file.

The code *contains* the document. It is not a link to one, so there is no
server to reach, no account, and nothing to expire. The app works with the
phone in aeroplane mode.

## Download

**[hods.apk](https://github.com/Feranmi-Jimba/hods-app/raw/main/hods.apk)** — 278 KB, Android 7 and above.

```
SHA-256  727788baed2d6aa241ef86f0715aaf2c4ff2dbf65c46dea2a89e767fc13570fb
```

## Installing

1. Open the link above on the phone. It downloads `hods.apk`.
2. Tap the downloaded file.
3. Android will ask permission to install apps from your browser — allow it.
4. Play Protect will say it has not seen this app before. Tap **More details**,
   then **Install anyway**.

That last step is not a warning about this app in particular. Android shows it
for every app that did not come from the Play Store, however ordinary.

## Using it

**Create** — choose a file. If it fits, you get one code. If it does not, you
get one *animated* code: a single image that plays every code it needs in
under five seconds. Either way it is one thing to send.

**Scan** — point the camera at a printed code, or use **Open a file** to read
an animated code straight from the file. Nothing goes to a network; the
document is rebuilt on the phone.

## Permissions

The app asks for the camera, to scan codes.

It has **no internet permission at all** — not withheld by policy, but absent
from the package, so it is incapable of sending anything anywhere. You can
check this yourself with `aapt dump permissions hods.apk`.
