# Onelap CN GPX Fix

An unofficial, free, offline GPX coordinate converter for the mainland Chinese version of Magene OnelapFit (顽鹿运动).

## The Problem

The Chinese OnelapFit application may incorrectly transform imported overseas GPX coordinates from WGS-84 through GCJ-02 to BD-09.

This was reproduced using a 44.9 km Singapore route exported from BRouter. After importing the original GPX, the Chinese OnelapFit server stored route coordinates displaced by approximately 1.12 km.

The same original route displayed correctly in global OnelapFit.

## The Solution

This converter pre-corrects GPX coordinates using the inverse transformation:

**BD-09 → GCJ-02 → WGS-84**

When Chinese OnelapFit subsequently applies its observed coordinate conversion, the resulting saved route aligns with the original WGS-84 coordinates.

The corrected Singapore test route was verified against the original BRouter track, and its map alignment was confirmed in the Chinese OnelapFit app.

## Features

- Runs on Windows and Android through a web browser
- Works offline after downloading the HTML file
- No Python installation required
- No firmware modification required
- Processes GPX files locally without uploading them to an external server
- Preserves original files and generates separate corrected GPX files

## Usage

1. Open the converter (`index.html`).
2. Select your original overseas GPX file.
3. Convert and save the corrected GPX.
4. Import the corrected GPX into Chinese OnelapFit.
5. Verify that the route aligns with the map before navigating.

## Important Limitations

- Intended for overseas routes affected by the verified Chinese OnelapFit coordinate-conversion issue.
- Do not use the corrected GPX directly with global OnelapFit, BRouter or other standard GPS applications.
- Do not indiscriminately convert mainland-China routes.
- The correction was verified against Chinese OnelapFit's saved route geometry and map display. On-device navigation behavior should be checked before relying on it during a ride.
- Future OnelapFit updates may change the import behavior.

## Disclaimer

This is an independent, unofficial project. It is not affiliated with or endorsed by Magene or OnelapFit.

Use at your own risk.
