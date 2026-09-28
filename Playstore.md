# Open with - Google Play Store listing

Character limits (Google Play): title max 30, short description max 80, full description max 4000.
Counts measured with a script on 2026-09-26: title 30/30, short 74/80, full 3,668/4,000. RECOUNT BEFORE PUBLISHING, and trade rather
than add.

THREE THINGS IN THIS FILE ARE LOAD-BEARING. Keep them true through every edit:

1. **No "no internet" claim, anywhere.** Play Billing and the in-app update library add INTERNET and
   ACCESS_NETWORK_STATE to the MERGED manifest. The app's own code opens no socket, so the honest
   claim is "Open with never sends your links or files anywhere". Same correction Bottom
   notifications made on 2026-09-22. Check the release merged manifest before writing anything
   stronger.
2. **The QUERY_ALL_PACKAGES paragraph ("WHY IT CAN SEE YOUR APPS") stays in the description.** It
   explains the permission before a reviewer, an antivirus product or a one-star review frames it,
   and it has to agree with the Permissions Declaration below.
3. **Nothing is advertised that is not built.** Everything listed is built (custom file types
   and the download-manager hand-off were added in Phase 11); none of it is verified on a device
   yet. **"SIGN-INS KEEP WORKING" in particular** rests on Phase 7's Samsung sign-in test, still
   `[todo]`: cut that section if the test fails. Recheck the animation count ("over 40") if
   styles are added or removed.

---

## App title (max 30 chars)

Open with: link & file chooser

(30 characters.) Plain "Open with" is shorter but collides with a crowd of existing listings in
search; the suffix says what it is.

---

## Short description (max 80 chars)

Take back control of every link, file and share. Make Android yours again.

---

## Full description (max 4000 chars)

TAKE BACK CONTROL. MAKE ANDROID YOURS AGAIN.

Android decides which app opens your links, files and shares, and since Android 12 it rarely even asks. Open with puts you back in charge. Pick any app on your phone, or set up rules once and let everything open where it should, automatically.

ADVANCED CONTROL
Choose any installed app, not just the ones Android suggests: Amazon links in the Amazon app, Reddit links in your favourite client, text files in the notepad you actually use.

AUTOMATED RULES
YouTube links always in YouTube Morphe. PDFs from Gmail in Acrobat. Never offer Chrome for Amazon links. Set it once, and it happens with nothing on screen.
- Match a website by name, wildcard (*.example.com), address prefix, a word it contains, or a regex.
- Scope a rule to a content type, to a file name, or to the app it came from.
- "Always ask" rules bring the chooser back for the things you want to decide each time.
- Hold any app in the chooser to make a rule on the spot, or to use that app for the next 10 minutes or the next 5 links.

FLEXIBLE
Links, video and audio streams, images, audio and video files, PDFs, ebooks, Word, Excel and PowerPoint files, text, archives, APKs, torrents, map locations, navigation, email addresses, phone numbers, text messages, Play Store links, web searches and shared items each get their own page: a default app, open without asking, hidden apps, sort order, remember the last app and their own countdown. Add your own file types too.

CUSTOMISABLE
A small chooser with a countdown, paused by any touch. Material You colours from your wallpaper, or your own. Grid or list, sizes, corners, width and position on screen, over 40 open and close animations, all with a live preview. Copy, edit or share a link before it opens, or hand it to your download manager.

WHEN SOMETHING DOESN'T ARRIVE
Most "it doesn't work" moments are Android, not the app: another app owns a website, or a phone maker's settings get in first. "Why isn't this working?" checks your setup, names the app holding a website, and shows the steps for your phone. Diagnostics shows exactly which rule would win for any link.

SIGN-INS KEEP WORKING
Open with answers custom tab requests, so app sign-ins that need a real browser tab (Samsung account and others) work with Open with as your default browser. Links that apps would show inside themselves can open in your real browser instead.

WHY IT CAN SEE YOUR APPS
Open with asks Android for the list of installed apps. That is how it can offer any app, not just the ones Android suggests, and how it finds the right apps for each type. The list is used on your phone only and never leaves it.

PRIVATE BY DESIGN
- No ads. No trackers. No analytics. No account.
- Open with never sends your links or files anywhere.
- Optional Debug Log, off by default, stays on your phone unless you share it.

FREE, WITH AN OPTIONAL ONE-TIME UPGRADE
Free: web links, all five kinds of website rule including "never offer", "always ask", "always open in the browser" and the app a link came from, hiding and ordering browsers, a default browser for links, the chooser and its colours, Material You, backup and restore, Diagnostics and the Debug Log, custom tab support and Android TV.

Open with Pro is a single one-time purchase, no subscription. It adds every other content type, the countdown, per-type settings, any app as a target, temporary choices, file name rules, your own file types, and the chooser's extra actions and looks.

GOOD TO KNOW
- Android 10 or newer. Works on phones, tablets and Android TV.
- Backups are files you keep.
- Never shows up in your recent apps.

Take back control of what opens where. Give it a try and make Android yours again.

---

## Play Console: Permissions Declaration for QUERY_ALL_PACKAGES

Required before the first upload, or it is rejected. Google permits the permission for apps that
"must discover any and all installed apps on the device, for awareness or interoperability purposes",
and names browsers among the examples. Open with holds the browser role and its core function is
launching arbitrary user-chosen apps, so file under **interoperability**.

Draft answer for the form's "core functionality" field:

> Open with is a link and file handler that lets the user choose which installed app opens each
> link, file, share or URI scheme, and it can be set as the device's default browser. Its core,
> user-facing function is offering and launching ANY installed app the user picks, including apps
> that do not declare an intent filter for that content (for example a notepad for text files, or a
> shopping app for its own web links). This is the most requested feature in this app category.
> Declared `<queries>` elements cannot cover this, because the target is by definition an app that
> declares no matching filter, so the set cannot be known in advance. The installed-app list is
> used on the device only, to populate the user's chooser and settings screens; it is never stored
> off the device or transmitted.

Draft answer for "why a less intrusive method will not work": the same last three sentences. Also
note in the form that the manifest keeps a full `<queries>` catalogue for every built-in content
type, so broad visibility is used ONLY for the "any installed app" picker and target selection.

Google will likely ask for a **video** showing the feature. Record: open a text file, tap "All apps"
in the chooser, pick a notepad that does not claim text files, and show it opening.

Prominent disclosure: the policy requires it where user data is collected. The app list never leaves
the device, so no separate consent dialog is planned; the description paragraph above and the
wording on the "All apps" picker are the disclosure. Revisit if the reviewer asks.

---

## Play Console: Data safety form

Draft answers, same as the sibling apps (Omnideck: "local-only, no off-device data"):

| Question | Answer |
| --- | --- |
| Does the app collect or share any required user data types? | **No** |
| Is all data encrypted in transit? | Not applicable (nothing is transmitted by the app) |
| Can users request data deletion? | Not applicable; clearing app data or uninstalling removes everything |

**One point to verify before submitting, not settled:** Google's guidance says purchase history read
through the Play Billing Library is financial data, and that data collected by third-party code
counts. Open with reads purchase state from the Play Store app on the device and sends it nowhere
itself. Check what Bottom notifications and Cordless declared (both use the same billing code) and
answer the same way, so the four house apps stay consistent.

---

## Store assets still to make

- Screenshots and feature graphic: `store_assets/make_store_assets.py` expects `Screenshots/` and an
  `OpenWith.png` at the project root. Neither exists yet.
- TV screenshots for a separate TV track (Phase 13).
- Play Store icon: `icon/ic_launcher-playstore.png`, downscaled to 512 on upload.
