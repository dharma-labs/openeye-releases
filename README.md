# openeye

a digital wellbeing app that counts what you actually watch, and gets out of the way.

free. no account, no ads, no tracking, no internet permission — nothing leaves your phone.

## download

[openeye-5.1.0.apk](https://github.com/dharma-labs/openeye-releases/releases/latest/download/openeye-5.1.0.apk)

1. tap the link, download the file
2. open it. android will say "for your security" — tap **settings** → **allow from this source**, then go back and install
3. open the app and walk through the three screens

requires android 8.0 or newer. about 1.6 mb.

sha256 of the apk: `f21c07134601bc33197fdd689b77b16b6993c96fcf74e72c197bcd9d737b1f78`

**if you already have an older openeye, uninstall it first.** 5.1.0 changed the app id, so android
sees it as a different app: installing it next to 4.x or 5.0.0 gives you two icons, not an update.
your watch history stays with the old one and goes when you remove it.

## stay updated without downloading anything

if you would rather not re-download the apk for every release, add this repository to
[F-Droid](https://f-droid.org/en/packages/org.fdroid.fdroid/) — the same app store openeye is being
submitted to, minus the waiting:

```
https://dharma-labs.github.io/openeye-releases/repo
```

in f-droid: **settings → repositories → new repository → enter a url manually**, paste the line
above, then **add repository**. openeye shows up under its own name; the first check for updates may
need a pull to refresh.

if you are reading this on your phone with f-droid already installed, you can paste this instead —
it opens the add-repository screen directly:

```
fdroidrepos://dharma-labs.github.io/openeye-releases/repo
```

what you get:

- new versions appear in f-droid's updates tab, and install over your existing one. your watch
  history and settings stay.
- the apk served there is byte-for-byte the one below — same sha256, same release key. it is not a
  rebuild, and nothing is re-signed behind the scenes.
- no account, no server of mine, nothing to log into. the index is a few static files on github.

what to know:

- f-droid asks you to allow installs from itself once, the same prompt as above.
- google play protect may say it "hasn't seen this app before" and offer to scan it. that happens
  for any apk that is not on the play store, including the one below.
- if openeye ever gets accepted into the main f-droid store, that copy is signed with f-droid's key,
  not mine, so the two channels cannot update each other. uninstall one before installing the other.

## what it does

- counts reel / shorts / tiktok time on the screen you are actually looking at — a small, quiet readout, not a dashboard
- reminds you of the number you already agreed to, while you are watching, not after
- can hide the reels / shorts button in instagram, and covers the apps you tell it to
- a tiny `today 42m` in the corner of the screen, always there, so you never have to open an app to
  know how long the phone has been on. it disappears inside feeds, because the feed readout is already there
- a home-screen widget with today's screen time and clip count
- shields, focus, and a numbers screen that only shows what was measured

## permissions

it asks for two, and that is all:

- **usage access** — so it can read the screen-time numbers android already keeps
- **accessibility** — so it can see which app is in front of you and show the reminder on top of it.
  it reads the package name on screen, and the on-screen labels it needs to find the reels/shorts
  button. nothing you type is read, recorded, or kept

there is no `INTERNET` permission in the apk, so it cannot send anything anywhere even if it wanted to. check it yourself with any apk viewer.

## source

[github.com/dharma-labs/openeye](https://github.com/dharma-labs/openeye) — GPL-3.0, buildable with
the gradle wrapper in the repo. the licence file, the fastlane store listing and the fdroid build
recipe are all in there, so nothing about this app has to be taken on trust.

## build

version `5.1.0` · build by dharmendra · signed with a release key, so future updates install over this one without uninstalling.

5.1.0 is the release cut: the app id moved to `io.github.dharma_labs.openeye`, the source went public
under GPL-3.0, and onboarding and the feed interrupt were re-laid out so they fit one screen each.
the way out of an interruption — "nah, go back" — is now always on the screen, never below the fold.

## uninstall

settings → apps → openeye → uninstall. removing it takes the widget with it; nothing is left behind and no data is stored on a server because no data ever leaves.

## problems

if the reminder never appears, the accessibility service was most likely killed by your phone's battery optimisation — turn off battery restriction for openeye and it comes back. on xiaomi, oppo and some samsung one ui builds, you also have to allow "display over other apps" for accessibility services in the developer options.

if the install fails with "app not installed", an older openeye is still on the phone. uninstall it and install again — the app id changed in 5.1.0.
