# HODS

Turn a document into a colour code you can print, send or scan — and turn it
back into the original file.

The code *contains* the document. It is not a link to one, so there is no
server to reach, no account, and nothing to expire. The app works with the
phone in aeroplane mode.

## Download

**[hods.apk](https://github.com/Feranmi-Jimba/hods-app/raw/main/hods.apk)** — 318 KB, Android 7 and above.

```
version  0.11
SHA-256  37fd62e3f5794b1ae37bb7304f47f7a8b94cbaa8700551c61f5733638b2cce33
```

This is the link to share, and the build in daily use.

### Please test this one — [hods-sealed.apk](https://github.com/Feranmi-Jimba/hods-app/raw/main/hods-sealed.apk)

```
version  0.13          321 KB
SHA-256  0383b3fb0a124d46c6a29a377853995188209d97187543db0a2ea04ed70087ca
```

0.13 is better in two ways that matter, and carries one change nobody has yet
run on a phone, which is why it is a separate file rather than the link above.

**Nothing is lost unless you ask.** There is a *keep it exact* switch and it is
ticked. Nothing is re-encoded, resized or transcoded: a 1.6 MB video comes back
byte for byte and plays in the app. A file that does not fit one code becomes as
many codes as it honestly needs, and the app says how many before you commit.
Untick it and pictures, video and sound are re-encoded far smaller — and the
result then says, plainly, that what came back is no longer the identical file.

**The app no longer ships readable.** Unzip it and you will not find the page,
the codec or the renderers. They are sealed with a key derived from the signing
certificate, so a repackaged copy resigned with another key refuses to run
instead of running as a convincing fake.

That sealing is also the untested part. The cryptography is proven — the real
Java was compiled and made to unseal the real files, byte for byte, and a wrong
key is refused — but no phone has served a sealed asset yet. If something is
wrong you will get a page that says so and prints the certificate digest it
computed, not a blank screen or a crash, and `hods.apk` above still works.

Install it over 0.11; codes made by any version open in any other.

## What it can carry

## What it can carry

A file is shrunk to fit before it is encoded, by something that understands what
kind of file it is:

| you give it | it does | measured |
|---|---|---|
| an uncompressed scan or photo | re-encodes it at print size | 5.0 MB → **one code** |
| a sound recording | re-encodes the audio | 689 KB → **one code** |
| a video | re-encodes it smaller | 1.6 MB → **one animation** |
| logs, telemetry, CSV, JSON, FASTQ | nothing — packing already gets 50–100× | untouched, byte for byte |
| an MP4, JPEG, ZIP or DOCX | nothing to take; already compressed | as-is |

Anything re-encoded comes back playable or openable and is renamed to match what
it now is. The app says plainly when it has done this, because the result is no
longer byte-identical. Text and data are never touched.

## Locking and signing

**Lock with a password** — the document is encrypted inside the code. Nobody
opens it without the password, including us. It is never stored and cannot be
recovered.

**Sign it as me** — proves the document came from your key, checkable offline by
anyone, and costs 64 bytes. The signature covers the file *and its name*, so a
signed document cannot be relabelled.

The app will not tell you a document is "verified". A signature proves that the
holder of one particular key produced those exact bytes; it says nothing about
who holds the key, and offline nothing can. So it reports the two facts
separately — whether the signature is sound, and whether this phone has been
told whose key it is — and shows the key's fingerprint so you can compare it
with whatever the issuer published, then name it.

## Reading it without saving it

Open a recovered file in the app, with nothing downloaded and nothing else
installed. You can still save it whenever you want to.

| | shown as |
|---|---|
| Word | **the document, laid out** — pages, styles, tables, headers, pictures |
| PDF | **the document, exactly** — drawn by the phone's own renderer, page by page |
| pictures, video, sound | themselves |
| text, CSV, JSON, logs | themselves |
| PowerPoint | its text, and the app says so — nothing small enough exists to lay out a deck |

Word is close to Word, not identical to it; no browser library manages identical.
PDF is exact, because a PDF is fixed-layout. The PDF viewer needs the installed
app — a browser has no renderer it can reach, and the app says that rather than
appearing broken.

Measured on real files: a 100-page deed comes back as 100 pages with its 20
tables intact, and a photographic schedule comes back as 100 pages with all 100
photographs.

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
