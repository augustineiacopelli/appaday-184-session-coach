# 184 Session Coach

Session Coach is a private, offline coaching companion for pregnancy center advocates who meet with fathers. After a session, the advocate logs which conversation areas he covered and how well he listened, and gets a score out of 100 with one strength, one area to grow and a next question to try. It also prints the talking points form, either blank or drafted from a session.

The app coaches the advocate on his own listening and topic coverage. It never evaluates the client. Every line of feedback describes what the advocate did, never what the father said or who he is.

Live app: https://augustineiacopelli.github.io/appaday-184-session-coach/

Category S. Day 184 of AppADay.

## Before any real use

Before any real use, confirm your center’s policy on recording and on keeping notes on a personal phone.

## How it scores

Coverage is worth 50 points: his heart and story 10, her and the baby 10, support and provision 10, and faith 20. Listening is worth 50 points: talk share 15 (full points at 35 percent or less, falling to zero at 75 percent), open questions 10, followed his lead 10, next steps 10 (his commitment 4, your commitment 3, a next meeting date 3) and ended with hope 5. Weights can be edited in Settings and are rescaled so each half still totals 50.

The feedback card names the strongest item as Went well, the weakest as To grow, and offers the next unused question from your question pool for the first area you did not cover, or from faith if you covered all four.

## Privacy model

Everything is stored in IndexedDB on your device and encrypted with AES GCM 256. The key is derived from your passphrase with PBKDF2 and SHA 256 at 600,000 iterations with a random salt, kept only in memory, and cleared after the idle limit (5 minutes by default), after 60 seconds in the background, and on wipe. Every write uses a fresh IV.

Session notes are purged at launch once they pass the retention limit (30 days by default) unless you mark them Keep longer. Scores are kept separately so your trend survives the purge. The retention number itself is stored unencrypted so the purge can run before you unlock.

The app makes no network requests of its own and never calls an AI service. The form tells you not to type his name, her name, dates of birth or ID numbers, and the initials field warns you if it looks like a full name. Opening a safety flag records only the flag type.

The encrypted backup is a JSON file that stays encrypted under the passphrase in use when it was made. You can restore it on a fresh phone from the first run screen, or merge it into an existing setup from Settings. The plain text summary is not encrypted, and the app warns you before it is made. Panic wipe deletes the whole database after you type WIPE.

## Your passphrase

There is no recovery. A forgotten passphrase means the data is gone. After five wrong tries the app waits 30 seconds before allowing another.

## Install to the home screen

Save the app to your home screen for durable storage. Browsers can clear storage for sites that are not installed, and Settings shows whether persistent storage has been granted.

## Printing

Print uses the system print dialog on US Letter with half inch margins. Page one is the conversation in six movements with ruled lines and a notes block. Page two is the advocate record. A blank print leaves every field empty. A drafted print fills in only the covered areas, both commitments, the next meeting date, materials, referrals, spiritual conversation and Gospel presented. It never prints initials, the score, flags, the session date or any identity or client field.

Some iOS versions do not allow printing from a home screen web app. Share print file builds the same form as a standalone HTML file and hands it to the share sheet, so you can save it to Files, open it and print it from there.

The printed form is a proposed revision of the male talking points for center review.

## Safety flags

Seven flags open step sheets with tap to call and tap to text links: danger right now, suicide or self harm, harm to her, the baby or others, abuse or control, pressure on her decision, a child may be at risk, and possible trafficking. The flag steps are general guidance until your center supplies its own protocol, and every step can be edited in Settings.

## Security header note

The page sets a strict Content Security Policy in a meta tag. frame-ancestors cannot be set from a meta tag on GitHub Pages, so framing protection depends on the host.

## Stretch tier status

The stretch tier, on device transcription of a Voice Memo with Whisper through a self hosted worker, is cut from this release. Its gate requires a real 5 minute Voice Memo to transcribe on an iPhone in under about 4 minutes without Safari reloading the page, and that test has not been passed. The app ships the core notes only tier, which defines complete. The area keyword lists and open question starters in Settings are kept for that future tier and are not used yet.

## Files

index.html is the whole app. There is no build step and no dependency beyond the shared AppADay save.js script.
