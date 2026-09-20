# HODS

Turn a document into a colour code you can print, send or scan — and turn it
back into the original file.

The code *contains* the document. It is not a link to one, so there is no
server to reach, no account, and nothing to expire. The app works with the
phone in aeroplane mode.

## Download

**[hods.apk](https://github.com/Feranmi-Jimba/hods-app/raw/main/hods.apk)** — 286 KB, Android 7 and above.

```
version  0.7
SHA-256  162cea2d431444fef934e4206113f882ae6be7024f99e591ba47a7b90ffe0e22
```

This is the link to share. It installs over an older copy without uninstalling
anything, and codes made by any version open in any other.

## Sending a code on WhatsApp

WhatsApp converts **every GIF it sends into a video**. That is what the app does
with GIFs; it is not a setting. Video compression works by mixing neighbouring
pixels together, and a code is its exact colours in exact places, so what lands
on the other phone reads as nothing at all.

So don't send the GIF there. Press **Save for WhatsApp (ZIP)**, then attach it
with the **paperclip → Document**. A zip is not media, so it arrives byte for
byte. The person receiving it opens it with **Scan → Open a file** — the app
looks inside and finds the code, so there is nothing to unzip.

Anywhere that sends a file as a file — email attachment, Drive, Telegram or
Signal as a document — the plain GIF is fine.

Never photograph a code off a screen and never send a screenshot of one. A
picture of a code is not the code.

## Installing

1. Open the link above on the phone. It downloads `hods.apk`.
2. Tap the downloaded file.
3. Android will ask permission to install apps from your browser — allow it.
4. Play Protect will say it has not seen this app before. Tap **More details**,
   then **Install anyway**.

That last step is not a warning about this app in particular. Android shows it
for every app that did not come from the Play Store, however ordinary.

## If it sticks on "Installing…"

Work down this list. The first item is by far the most common.

**1. Uninstall any earlier copy of HODS first.**
Android refuses to install an app over an existing one with the same name
unless both were signed with the same key, and some installers — Samsung's in
particular — report that refusal as a progress bar that never finishes rather
than as an error. If HODS is already on the phone from an older build, remove
it (long-press the icon → Uninstall), then install again. Nothing else fixes
this one.

**2. Samsung phones: turn off Auto Blocker.**
Settings → Security and privacy → Auto Blocker. It is on by default on recent
One UI versions and it blocks installing apps from anywhere but the Play Store.
Turn it off, install, and turn it back on afterwards if you like.

**3. Restart the phone.**
A package installer that has got itself stuck stays stuck until it is
restarted, and every later attempt joins the same queue. If the first attempt
hung, the third will too.

**4. Check the file is really 281 KB.**
If it was saved from the repository's web page instead of the download link,
what landed may be a web page named `hods.apk`. Re-download using the link
above.

**5. Install from Files, not from the browser's download notification.**
Open the phone's Files app, find `hods.apk` in Downloads, and tap it there.
Some browsers hand the file to an installer that behaves differently.

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
