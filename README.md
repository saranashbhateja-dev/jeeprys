# JEE OS 4.0.0 — New Curriculum Build

This is a fresh JEE OS build based on the uploaded `data(1).md`. The old `Jee OS(10).zip` is used as a reference for the UI, planner, revision system, Sunday tests, DPP/practice tracking, Supabase cloud sync, and Android build workflow.

## Curriculum
- Start date: **29 October 2026**
- Physics: 31 chapters / 196 lectures
- Chemistry: 33 chapters / 257 lectures
- Mathematics: 30 chapters / 205 lectures
- Total: **94 chapters / 658 lectures**
- The chapter order, lecture counts, and URLs are copied from the supplied data file.

## Daily plan
Every non-Sunday study day schedules six lectures in this order: Physics 1–2, Chemistry 1–2, Mathematics 1–2. Each subject progresses independently through its supplied chapter order. Each scheduled lecture has its own persistent DPP checkbox, plus one date-specific practice checkbox for each subject. Sundays remain reserved for the existing test/rest system.

## Revision and tests
The six-cycle spaced revision system and the reference OS's Sunday test framework are retained. Revision starts after all lectures in a chapter are completed. Test results, weak areas, and score history remain trackable.

## Desktop launch (Windows)
1. Install Node.js 22 or newer.
2. Extract this ZIP to a writable folder.
3. Run `start.bat`.
4. The app opens at `http://127.0.0.1:3000`. Do not open `index.html` directly.

## Supabase cloud sync
The app retains the Supabase project URL and publishable key from the reference OS. Sign in using the same account on desktop and Android to sync progress. State is saved locally first and then synchronized to `jeeo_cloud_state`; row-level security remains scoped to the authenticated user. The new `curriculumId` prevents the app from loading an older curriculum snapshot into this build. On first sign-in, an older snapshot is replaced with this new curriculum's fresh state.

For safety, only the Supabase publishable key is used in the client; never put a service-role key in this app.

## Android APK
The GitHub Actions workflow builds a debug APK on push to `main` or via **Actions → Build JEE OS 4.0 APK → Run workflow**. Download the artifact named `JEE-OS-4.0-debug-apk`. The APK is built by GitHub Actions; this ZIP does not contain a prebuilt APK.
