# Junior School Exam Analyzer (extracted subsystem)

Extracted from the Charanas Analyzer system. Scoped to the **Junior School**
exam-analysis workflow only.

## Included modules
- **Dashboard** – quick stats
- **Subjects** – manage junior-school subjects (pathway/senior subjects excluded)
- **Classes & Streams** – set up grades and streams
- **Students** – enrol students into streams
- **Exams** – the full analysis pipeline:
  - Create Exam
  - Exam Timetable
  - Exam List
  - Upload / Enter Marks
  - Analyse (per-stream, per-subject, grade distribution, etc.)
  - Merit List
  - Summary Analytics
  - Report Forms
- **Settings** – locked to "Junior School (No Pathways)"

## Removed
- Platform Admin (Schools, Broadcast, Access Control, Bug Detector, etc.)
- Teachers / Staff Details / People
- Timetables (lesson)
- Papers & Resources
- Finance / Fees / Salaries / Payslips
- Messaging
- Live Chat

The DOM for these sections is intentionally left in place but unreachable —
this avoids breaking the many cross-references inside `script.js`. The
sidebar exposes only the junior exam-analysis surface.

## Run it
Open `index.html` in a modern browser (or serve the folder with any static
server, e.g. `python3 -m http.server`). On first launch you will be asked to
create a Platform/Admin login — that account becomes the school admin for
this local copy. The school level is hard-locked to **junior**.

## Files
- `index.html` – UI shell (sidebar trimmed)
- `script.js` – original app logic + a top-of-file guard that:
  - forces `settings.schoolLevel = 'junior'`
  - hides the platform-admin sidebar/navbar/topbar
  - hides non-exam navigation entries
- `styles.css` – original styles
- `supabase-sync.js` – optional cloud sync (unchanged; safe to ignore)
- `results.html` – public results lookup page (kept; remove if not needed)
