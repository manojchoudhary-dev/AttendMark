# AttendMark — No-Proxy Class Attendance System

**Live site:** https://attendmark-zeta.vercel.app

## The Problem

Taking attendance in a classroom the usual way — calling out names or passing a sheet — is slow, and proxy attendance is easy: a student can sign for an absent friend, or share a static code/photo with the whole class. A 5-minute job eats into teaching time every single lecture.

## The Solution

AttendMark makes attendance fast for the teacher and hard to fake for students:

- The **teacher logs in** and starts a session for the class.
- The screen shows a **QR code with a join link**, a big **session code**, and a **rotating code that changes every 15 seconds** — a screenshot of the code is useless within seconds.
- **Students have no separate entry point.** They scan the teacher's QR, the marking form opens with the session already filled in, and they enter the current rotating code, their name and scholar number.
- A scholar number can mark **only once per session** — a second attempt is blocked as **"Already marked"**, and blocked attempts are shown to the teacher.
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
