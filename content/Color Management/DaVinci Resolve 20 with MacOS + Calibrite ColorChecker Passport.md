## Purpose

This guide explains how to set up DaVinci Resolve color management, apply color calibration using a ColorChecker chart

## Overview

You will:

1. Open DaVinci Resolve project settings.
2. Configure color management.
3. Import the video footage.
4. Rotate vertical footage if needed.
5. Add a Color Space Transform node.
6. Add a Color Match node.
7. Add a final Color View / Output Transform node.
8. Export for Instagram Reels.

---

## 1. Open Project Settings

In DaVinci Resolve, click the **Project Settings** icon in the bottom-right corner of the interface.

![[attachments/Screenshot-2026-05-26-at-1.24.33-PM-7e5f09b08b.png]]

---

## 2. Configure Color Management

Go to:

**Project Settings → Color Management**

Use the following settings:

|Setting|Value|
|---|---|
|Color Science|DaVinci YRGB|
|Timeline color space|DaVinci WG/Intermediate|
|Output color space|Rec.709 Scene|

![[attachments/Screenshot-2026-05-26-at-12.19.18-PM-b955386057.png]]

Click **Save** when finished.

---

## 3. Import the Video Footage

Import the video footage into DaVinci Resolve.

You can now begin the color calibration workflow.

---

## 4. Rotate Vertical Footage

For vertical video, the footage may import with the wrong orientation. If needed, rotate the clip before color matching.

Right-click the footage and go to:

**Clip Attributes → Image Orientation → 90° Left (base on you footage)→ OK**

![[attachments/Screenshot-2026-05-26-at-1.25.42-PM-copy-2-91de787b84.png]]

---

# Color Calibration Workflow

## 5. Go to the Color Page

Open the **Color** page in DaVinci Resolve.

---

## 6. Add the Color Space Mapping Node

In the node graph, select the first node.

Open the **Effects Library**, search for **Color Space Transform**, and drag it onto the first node.

This first node will be the **Color Space Mapping Node**.

![[attachments/Screenshot-2026-05-26-at-1.26.34-PM-ac91425bf9.png]]

---

## 7. Set the Input Color Space and Gamma

The **Input Color Space** and **Input Gamma** should match the camera footage settings.

For example, if the footage was shot with Sony S-Gamut3.Cine and Sony S-Log3, use:

|Setting|Value|
|---|---|
|Input Color Space|Sony S-Gamut3.Cine|
|Input Gamma|Sony S-Log3|
|Output Color Space|DaVinci Wide Gamut|
|Output Gamma|DaVinci Intermediate|

Using **DaVinci Wide Gamut / DaVinci Intermediate** gives more room for grading.

![[attachments/Screenshot-2026-05-26-at-1.27.22-PM-20e6b96c0e.png]]

---

# Color Match Node

## 8. Add a Corrector Node

Right-click an empty area in the node graph and select:

**Add Node → Add Corrector**

This node will be used for color matching.

![[attachments/Screenshot-2026-05-26-at-1.27.42-PM-copy-3a48e5f0d8.png]]

---

## 9. Match the Color Chart

Go to the **Color Match** panel.

Select the color chart target used in the footage.

Example:

**Calibrite ColorChecker Passport Video**

Then, in the viewer, position the color chart grid over the chart in the video frame.

Once the chart is aligned correctly, click **Match** in the Color Match window.

![[attachments/Screenshot-2026-05-26-at-1.30.08-PM-copy2-2ab2d36af7.png]]

---

# Color View Node

## 10. Add the Final Corrector Node

Right-click an empty area in the node graph and select:

**Add Node → Add Corrector**

This will become the final viewing/output transform node.

![[attachments/Screenshot-2026-05-26-at-1.30.08-PM-copy-5002178a97.png]]

---

## 11. Add Color Space Transform to the Final Node

Search for **Color Space Transform** in the Effects Library and drag it onto the last node.

This node will be the **Color View Node**.

![[attachments/Screenshot-2026-05-26-at-1.30.25-PM-d268b1b39c.png]]

---

## 12. Set the Output Transform

The input settings should match the output from the first node:

|Setting|Value|
|---|---|
|Input Color Space|DaVinci Wide Gamut|
|Input Gamma|DaVinci Intermediate|
|Output Color Space|Rec.709|
|Output Gamma|Gamma 2.4|

For consistent color, **Rec.709 / Gamma 2.4** is recommended for this workflow.

![[attachments/Screenshot-2026-05-26-at-1.30.43-PM-b9a71614d9.png]]

At this point, the footage should be color calibrated.

---

# Instagram Reels Export Settings

Go to the **Deliver** page and use the following export settings:

|Setting|Value|
|---|---|
|Format|MP4|
|Codec|H.265|
|Resolution|1080 × 1920|
|Quality|Restrict to 30000 Kb/s|

![[attachments/Screenshot-2026-05-26-at-1.36.28-PM-b08cc3a636.png]]

---

# Recommended Node Structure

Use this node order:

1. Color Space Mapping Node   Camera color space/gamma → DaVinci Wide Gamut / DaVinci Intermediate
2. Color Match Node   ColorChecker chart calibration
3. Color View Node   DaVinci Wide Gamut / DaVinci Intermediate → Rec.709 / Gamma 2.4
---

# Notes

The camera input color space and gamma must match the actual footage settings. For example, Sony S-Log3 footage should use Sony S-Log3 as the input gamma.

For consistent results, shoot the ColorChecker chart under the same lighting conditions as the footage.