---
title: "Web Interface"
description: "Complete guide to NanoDLP web interface features, API endpoints, and user interface functionality."
lead: "Learn how to use NanoDLP's web interface for printer control, file management, and system configuration."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---

## Overview

NanoDLP’s web interface is where you perform day‑to‑day work: upload files, slice, start/stop prints, and monitor the machine. This page shows how to complete the most common tasks quickly.

## Access the interface

1. Find your printer’s IP on your network UI or screen.
2. Open a browser and go to: `http://<printer-ip>/`.
3. If authentication is enabled, sign in with your user credentials.

## Quick start: from model to print

1. Upload a model
   - Go to Plates or Jobs and choose Add/Upload.
   - Select your file (STL, 3MF, OBJ, ZIP with PNGs, etc.).
2. Pick a profile
   - Choose a resin profile appropriate for your material. If unsure, start with your manufacturer’s recommendation and fine‑tune later. See [Profile Management]({{<ref "profiles">}}).
3. Slice
   - Slice locally (server), in the browser ([Web‑based Slicing]({{<ref "web-based-slicing">}})), or remotely.
4. Start printing
   - Open the created plate/job and click Print. Confirm when prompted.
5. Monitor progress
   - Home shows layer, ETA, and status. Use Pause/Resume/Stop as needed.

## Everyday tasks

### Upload or import
- Upload from your computer: Add/Upload in Plates or Jobs.
- From USB: Insert the drive and open USB in the sidebar to select files.

### Re‑slice after changes
- If you change profile parameters that affect slicing, click Regenerate on the plate to re‑apply settings. See indicators in [Settings Overview]({{<ref "settings">}}).

### Pause, resume, stop
- Pause: Safely pauses after the current exposure/move.
- Resume: Continues the job.
- Stop/Force stop: Stops immediately; use with caution.

### Estimate time/material
- Use Estimate on a profile/height or view estimates on the job page after slicing.

### Backup and restore
- Create a backup from Setup/Backup. Restore from the same section. See [Guide → Backup]({{<ref "guide/backup">}}).

## Where to find things

- Home: Live status, current job, quick actions.
- Plates/Jobs: Upload, manage, regenerate, print.
- Profiles: Create/tune resin profiles. See [Profile Management]({{<ref "profiles">}}).
- Machine/Setup: Pins, motors, display, network, and advanced options. See [Machine Configuration]({{<ref "machine-configuration">}}).
- Terminal: Send G‑code and view logs.
- WiFi: Configure network. See [Raspberry Pi display/WiFi]({{<ref "guide/raspberry-pi-display">}}).

## Troubleshooting

- Can’t reach the UI: Verify IP, network, and that NanoDLP service is running. Try another browser.
- Upload fails: Check file size/format. For large files, prefer server or remote slicing.
- Slicing stuck: Review logs on Terminal; try Web‑based Slicing or Remote Slicing.
- Print won’t start: Ensure no active job, doors/sensors OK (if enabled), and sufficient free space.

## Next steps

- Configure your printer hardware: [Machine Configuration]({{<ref "machine-configuration">}})
- Create a working resin profile: [Profile Management]({{<ref "profiles">}})
- Slice in the browser: [Web‑based Slicing]({{<ref "web-based-slicing">}})
