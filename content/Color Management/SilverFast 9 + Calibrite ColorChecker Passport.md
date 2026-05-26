# Creating and Using a Scanner ICC Profile

here is GTX980 icc profile I made
![[attachments/GTX980-13058bcb5e.icc]]

## Purpose

This workflow explains how to create a custom ICC profile from a scanned calibration card and use it in SilverFast for future scans.

## Overview

You will:

1. Scan the calibration card with no input profile selected.
2. Open the scanned image in Adobe Camera Raw.
3. Save the file as a 16-bit TIFF.
4. Import the TIFF into Calibrite Profiler.
5. Create an ICC profile from the TIFF.
6. Save or move the profile to the system color profile folder.
7. Restart SilverFast and select the new profile.

---

## 1. Scan the Calibration Card

In SilverFast, scan the calibration card with the **Input Profile** set to **None**.

This ensures the scan is captured without an existing color profile affecting the result.
here I am using Calibrite Colorchecker classic as target.

![[attachments/Screenshot-2026-05-26-103941-4dcab08887.png]]

---

## 2. Open the Scan in Adobe Camera Raw

Open the scanned calibration card image in **Adobe Camera Raw**.

Do not apply creative edits, color corrections, or automatic enhancements. The goal is to preserve the scanned target as accurately as possible.

![[attachments/Screenshot-2026-05-25-at-12.42.28-PM-2b01443130.png]]

---

## 3. Save as a 16-Bit TIFF

Export or save the file as a **TIFF** with the following setting:

|Setting|Value|
|---|---|
|File format|TIFF|
|Bit depth|16 bits/channel|

Save the TIFF somewhere easy to find.

---

## 4. Import the TIFF into Calibrite Profiler

Open **Calibrite Profiler** and choose the camera profiling workflow.


![[attachments/Screenshot-2026-05-26-at-11.21.01-AM-d078116e00.png]]

under ICC-TIFF section, Import the saved TIFF file.  and then create profile and save it to icc profiles folder on you computer

![[attachments/Screenshot-2026-05-25-at-12.43.18-PM-081b595d90.png]]

---

## 5. Save the ICC Profile

After Calibrite Profiler creates the ICC profile, save or move it to the correct system profile folder.

### macOS

```
Macintosh HD / Library / ColorSync / Profiles
```

### Windows

```
C:\Windows\System32\spool\drivers\color
```

Use a clear profile name so it is easy to identify later, for example:

```
Scanner_Model_CalibrationCard_Date.icc
```

---

## 6. Restart SilverFast

Close and reopen **SilverFast** so it can detect the newly installed ICC profile.

---

## 7. Select the New Profile in SilverFast

In SilverFast, go back to the input profile settings and select the newly created ICC profile.

Use this profile for future scans made with the same scanner and scanning setup.

![[attachments/Screenshot-2026-05-26-113507-8d5401d38a.png]]

---

## Notes

The profile should be recreated if the scanner settings, lighting conditions, film holder, calibration target, or workflow changes significantly.

For consistent results, always use the same scanning settings that were used when the calibration card was scanned.

