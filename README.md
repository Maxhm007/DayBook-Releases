# DayBook for Windows

Download the latest Windows installer from [Releases](https://github.com/Maxhm007/DayBook-Releases/releases/latest). Use the x64 setup EXE for a normal per-user installation; MSI is also available.

DayBook provides an offline daily journal with task dates/times, priority, status, completion timestamps, search, Summary and Trash. Entries are stored locally in SQLite.

## Google setup

Cloud features require an operator-configured Google Desktop OAuth client and hosted DayBook gateway. This release does not ship working production Google credentials or a hosted sync service. You can use the local journal immediately.

The operator must configure the OAuth consent screen, enable Google Sheets access, provide the native client ID/installed-app secret, deploy one HTTPS gateway process, and share the private **DayBook Database** workbook with the server's service account. Each Google user has a separate worksheet; users do not get direct access to other users' tabs. No Supabase or Firebase is used.

Open **Settings**, enter the Desktop client ID, installed-app secret and gateway base URL, then choose **Sign in with Google**. Authentication opens your system browser. Refresh tokens stay in Windows Credential Manager. Local-only and Google-account journals are separate workspaces.

## Updates

DayBook checks the signed GitHub update feed on startup and every four hours. Updates download automatically and install only when the journal is idle with no waiting edits. Windows may close/restart the app during installation. Settings provides manual check/install controls.

Updater signatures verify the update publisher key. This version does not have Windows Authenticode publisher signing, so Windows may show an unrecognized publisher notice. Never use an installer from an untrusted source.

Live Google login, two-device sync and clean-machine upgrade qualification remain outstanding. Build/test status appears in [Actions](https://github.com/Maxhm007/DayBook-Releases/actions). Source is maintained separately in the private Maxhm007/DayBook repository.
