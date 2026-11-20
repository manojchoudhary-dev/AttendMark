# AttendMark — No-Proxy Class Attendance System

**Live site:** https://attendmark-zeta.vercel.app

## The Problem

Taking attendance in a classroom the usual way — calling out names or passing a sheet — is slow, and proxy attendance is easy: a student can sign for an absent friend, or share a static code/photo with the whole class. A 5-minute job eats into teaching time every single lecture.

## The Solution

AttendMark makes attendance fast for the teacher and hard to fake for students:

- The **teacher logs in** and starts a session for the class.
- The screen shows a **QR code with a join link**, a big **session code**, and a **rotating code that changes every 25 seconds** — the QR rotates with the code, so a screenshot is useless within seconds.
- **Students have no separate entry point.** They scan the teacher's QR and only the marking form opens — the session and rotating code are filled in automatically and never shown to the student; they enter just their name and scholar number.
- A scholar number can mark **only once per session** — a second attempt is blocked as **"Already marked"**.
- **Location check:** the session captures the teacher's classroom location, and a student can mark only within 150 metres of it; the register shows each entry's distance from the class.
- **Device lock:** one device can mark only once per session — after a successful mark, the same phone cannot open the marking form for that session again.
- **Red-flag detention system:** a second actual submit (same scholar number again, or a second entry from a device that already marked) is recorded and shown to the teacher in a red **Flagged Attempts** panel, labelled **FLAGGED — FOR DETENTION**, with the scholar number, name, time and reason. The flags are included in the CSV download and in the emailed register.
- The teacher watches a **live register** fill up in real time, can **download a CSV**, or send the register to their email in one click.

## Roles

| Role | Access |
| --- | --- |
| **Teacher** | Email login; own sessions, live registers, history, CSV/email export |
| **Student** | No login and no home-page entry — joins only through the teacher's live QR/session |
| **Admin** | Authorised admin accounts see all teachers, all sessions and all attendance data, with a full CSV export |

## Tech Stack

- **Frontend:** a single self-contained `index.html` (HTML, CSS, JavaScript) — no build step
- **Backend:** Firebase Authentication (email/password) + Cloud Firestore (sessions and attendance records)
- **Hosting:** Vercel (auto-deploys from this repository)

## Project Info

- **Built by:** Manoj Choudhary
- **Scholar Number:** 26U020146
- **Subject:** FoCP (CSE-1003)
- **Institute:** IIIT Bhopal

The site footer carries the Privacy Policy and Terms of Use. Demo Mode on the site previews the complete flow without creating an account.
