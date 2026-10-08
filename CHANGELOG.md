# Changelog

## 2026-10-08

- Added **Bookshelf Lamp — Accent Cyan**, an independent optional ambient-light preset (Color mode, cyan hue, brightness 20%, saturation 25%) validated visually in a Teams call.
- Documented the rationale: sober, professional and appropriate for frequent calls; may be kept on routinely or switched off without changing any HOYA/CPL Camera Hub or Key Light profiles.
- Replaced outdated Bookshelf Lamp 100% baseline wording; registered the dedicated iOS screenshot in `screenshots/MANIFEST.json` and placed its JPEG in the camera-independent `screenshots/source-extracts/configurazioni trasversali illuminazione/` directory.

- Calibrated the HOYA UXII UV Facecam 4K profile and approved its visual quality in a real Microsoft Teams call (2026-10-08).
- HOYA Camera Hub exposure/color/processing: 1/33 s, ISO 2483, 4900 K / Tint -3, Contrast 55%, Saturation 60%, Sharpness 45%, Noise Reduction Custom 2D 40 / 3D 34; Zoom/FOV 174%.
- HOYA Key Light Air profile: Left 30%, Right 20%, both 5400 K; bookshelf lamp off during testing.
- Added four HOYA screenshot entries to `screenshots/MANIFEST.json` and linked evidence in sections 10.3.2 and 11.2.2.
- **Resolved:** replaced the incorrect HOYA Frame & Picture screenshot, confirming 1080p30 (YUY2 raw), matching the calibration. Closed the capture-format discrepancy; CPL values and screenshot archives unchanged.

- Explicitly confirmed **HOYA UXII UV (49 mm)** as the standard, permanently mounted filter on the Elgato Facecam 4K since 2026-10-05 (not CPL).
- Recorded the rationale: HOYA UV is essentially neutral for visible-light transmission; the alternative CPL reduces transmitted light and costs exposure stops, requiring compensation.
- Preserved the validated CPL Camera Hub + Key Light Air profile (2026-10-01); HOYA calibration subsequently completed and approved in Teams on 2026-10-08.
- Clarified the Facecam validation note to distinguish the CPL baseline from the HOYA profile, subsequently validated on 2026-10-08.

## 2026-10-05

- Reorganized Facecam 4K Camera Hub and Elgato Key Light Air settings into filter-specific configuration profiles.
- Preserved the 2026-10-01 Camera Hub and Key Light Air baseline as the validated profile for `Elgato Facecam 4K + Filtro K&F Concept CPL Nano-Klear`.
- Registered `HOYA UXII UV` as the default filter mounted on the Elgato Facecam 4K from 2026-10-05; its dedicated Camera Hub and Key Light Air profile is pending calibration.
- Moved the three Camera Hub screenshots and the Key Light Air screenshot into `screenshots/source-extracts/configurazioni per uso di Elgato Facecam 4K + Filtro K&F Concept CPL Nano-Klear/`.
- Updated `screenshots/MANIFEST.json` to reflect the new evidence paths and profile association.

## 2026-10-01

- Updated Elgato Key Light Air production baseline.
- Confirmed naming convention from Salvatore's point of view: Left = his left; Right = his right.
- Set Key Light Air Left to 50% / 5400 K.
- Set Key Light Air Right to 35% / 5400 K.
- Baselined Elgato Facecam 4K Camera Hub settings and device details.
- Replaced legacy Facecam screenshot references with the three dated 2026-10-01 screenshots.
- Standardized Facecam and Key Light screenshot naming and registered the four current screenshots in `screenshots/MANIFEST.json`.

## 2026-07-20

- Created initial Git-ready archive.
- Consolidated OBS 32.1.2 production settings.
- Consolidated Blue Yeti and RØDE PodMic filter chains.
- Recorded TDR Nova GE, Kotelnikov, Limiter and Wider values.
- Recorded global audio-track routing and +80 ms PodMic sync offset.
- Recorded Vocaster Two settings, including 48V Off, Radio Enhance, Rumble Reduction High and gain set through Auto Gain calibration.
- Corrected Sony `Rec. Media During HDMI Output` to On.
- Recorded Elgato Game Capture 4K X production values.
- Recorded Logitech StreamCam / Logi Tune production values.
- Added source documents and extracted embedded screenshots.
