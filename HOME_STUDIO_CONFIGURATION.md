# Home Studio Configuration — Single Source of Truth

**Owner:** Salvatore Larosa  
**Version:** 2026-08-03  
**Status:** Production baseline  
**Purpose:** fotografia tecnica dello stato attuale del sistema Home Office / Home Studio.  
**Rule:** i valori indicati come `Production` descrivono ciò che è attualmente configurato. Alternative, ipotesi e prove future sono riportate separatamente e non sostituiscono la baseline.

## 1. Principi operativi

- La Sony ZV-E10 MK2 produce il master principale su SD.
- OBS svolge funzioni di regia, composizione, streaming, virtual camera e registrazione di sicurezza.
- La gestione audio deve restare centralizzata a livello globale in OBS, non duplicata nelle singole scene.
- Deve essere attiva una sola catena voce principale alla volta.
- Blue Yeti è destinato ai workflow rapidi; RØDE PodMic + Vocaster Two ai workflow importanti.
- I test di sync vanno verificati con speaker integrati del Mac o cuffie cablate, non tramite AirPlay/HomePod.
- La Logitech StreamCam è stata dismessa: la webcam secondaria Production è ora Elgato Facecam 4K.
- La Facecam 4K può usare filtri ottici da 49 mm; i filtri vanno trattati come parte della configurazione video, non come accessori generici.
- Per workshop/seminari fuori studio è disponibile il kit DJI Wireless Mic 3.

## 2. Ambiente

| Parametro | Valore | Stato |
|---|---|---|
| Computer principale | MacBook Pro 2024, M3 Pro, 36 GB RAM | Production |
| OBS Studio | 32.1.2 | Production |
| Sistema video principale | Sony ZV-E10 MK2 + Elgato Game Capture 4K X | Production |
| Webcam secondaria | Elgato Facecam 4K + cavo Elgato USB-C 5 Gbps | Production |
| Webcam precedente | Logitech StreamCam | Retired / dismessa |
| Microfono principale | RØDE PodMic tramite Focusrite Vocaster Two | Production |
| Microfono alternativo | Blue Yeti USB | Production |
| Routing audio virtuale | BlackHole 2ch | Installed / On demand |

# 3. OBS Studio

## 3.1 General

| Parameter name | Current value |
|---|---|
| Language | English (UK) |
| Open stats dialogue on startup | Off |
| Update Channel | Stable - Latest stable release (Default) |
| Automatically check for updates on startup | On |
| Show confirmation dialogue when starting streams | On |
| Show confirmation dialogue when stopping streams | On |
| Show confirmation dialogue when stopping recording | Off |
| Automatically record when streaming | On |
| Keep recording when stream stops | On |
| Source Alignment Snapping — Enable | On |
| Snap Sensitivity | 10.0 |
| Snap Sources to edge of screen | On |
| Snap Sources to other sources | On |
| Snap Sources to horizontal and vertical centre | On |
| Hide cursor over projectors | On |
| Search known locations for scene collections when importing | On |
| Show preview/program labels | On |
| Show scene names | On |
| Multiview Layout | Horizontal, Top (8 Scenes) |

## 3.2 Stream

| Parameter name | Current value |
|---|---|
| Service | YouTube - RTMPS |
| Server | Primary YouTube ingest server |
| Ignore streaming service setting recommendations | Off |

## 3.3 Output — General

| Parameter name | Current value |
|---|---|
| Output Mode | Advanced |

## 3.4 Output — Streaming

| Parameter name | Current value |
|---|---|
| Audio Track | 1 |
| Audio Encoder | CoreAudio AAC |
| Video Encoder | Apple VT H264 Hardware Encoder |
| Rescale Output | Disabled |
| Rate Control | CBR |
| Bitrate | 12000 Kbps |
| Keyframe Interval | 2 s |
| Profile | High |
| Use B-Frames | On |
| Spatial AQ | Automatic |

### Note
Configurazioni alternative sono state discusse in passato, ma questa sezione fotografa esclusivamente i valori attualmente in produzione.

## 3.5 Output — Recording

| Parameter name | Current value |
|---|---|
| Type | Standard |
| Recording Path | `/Users/slarosa/Movies/OBS` |
| Generate File Name without Space | Off |
| Recording Format | Matroska Video (.mkv) |
| Video Encoder | Apple VT H264 Hardware Encoder |
| Audio Encoder | CoreAudio AAC |
| Audio Tracks | 1, 2 |
| Rescale Output | Disabled |
| Rate Control | CBR |
| Bitrate | 12000 Kbps |
| Keyframe Interval | 2 s |
| Profile | High |
| Use B-Frames | On |
| Spatial AQ | Automatic |
| Automatically remux to mp4 | On |

## 3.6 Output — Audio Tracks

| Track | Audio Bitrate | Logical use |
|---|---:|---|
| Track 1 | 160 Kbps | Main mix |
| Track 2 | 160 Kbps | Blue Yeti isolated |
| Track 3 | 160 Kbps | RØDE PodMic isolated |
| Track 4 | 160 Kbps | Unused |
| Track 5 | 160 Kbps | Unused |
| Track 6 | 160 Kbps | Unused |

## 3.7 Replay Buffer

| Parameter name | Current value |
|---|---|
| Enable Replay Buffer | Off |
| Maximum Replay Time | 20 s |

## 3.8 Audio

| Parameter name | Current value |
|---|---|
| Sample Rate | 48 kHz |
| Channels | Stereo |
| Desktop Audio | BlackHole 2ch |
| Desktop Audio 2 | Disabled |
| Mic/Auxiliary Audio | Device not connected or not available |
| Mic/Auxiliary Audio 2 | Device not connected or not available |
| Mic/Auxiliary Audio 3 | Disabled |
| Mic/Auxiliary Audio 4 | Disabled |
| Decay Rate | Fast |
| Peak Meter Type | True Peak (Higher CPU usage) |
| Monitoring Device | Vocaster Two USB |
| Low Latency Audio Buffering Mode | Off |

## 3.9 Video

| Parameter name | Current value |
|---|---|
| Base (Canvas) Resolution | 1920×1080 |
| Output (Scaled) Resolution | 1920×1080 |
| Downscale Filter | No downscaling required / resolutions match |
| Common FPS Values | 25 PAL |

## 3.10 Advanced

| Parameter name | Current value |
|---|---|
| Renderer | Metal (Experimental) |
| Colour Format | NV12 (8-bit, 4:2:0, 2 planes) |
| Colour Space | Rec. 709 |
| Colour Range | Limited |
| SDR White Level | 203 nits |
| HDR Nominal Peak Level | 1000 nits |
| Disable macOS V-Sync | On |
| Reset macOS V-Sync on Exit | On |
| Show active outputs warning on exit | On |
| Filename Formatting | `%CCYY-%MM-%DD %hh-%mm-%ss` |
| Overwrite if file exists | Off |
| Automatically remux to mp4 | On |
| Automatically Reconnect | On |
| Retry Delay | 2 s |
| Maximum Retries | 20 |
| IP Family | IPv4 and IPv6 (Default) |
| Bind to IP | Default |
| Dynamically change bitrate to manage congestion | Off |
| Enable Browser Source Hardware Acceleration | On |
| Hotkey Focus Behaviour | Disable hotkeys when main window is not in focus |

## 3.11 Permissions macOS

All permissions shown in OBS are granted:

- Screen Recording
- Camera
- Microphone
- Input Monitoring

## 3.12 Global audio sources and tracks

| Source | Track 1 | Track 2 | Track 3 | Audio Monitoring |
|---|---:|---:|---:|---|
| Blue Yeti | On | On | Off | Monitor Off |
| RØDE PodMic | On | Off | On | Monitor Off |
| VIDEO / BlackHole | On | Off | Off | Monitor Off |

### Centralization rule
The audio sources and their filters are global. They must not be duplicated independently inside individual scenes.

## 3.13 Sync Offset baseline

| Audio chain | Sony + Game Capture 4K X | Elgato Facecam 4K |
|---|---:|---:|
| RØDE PodMic → Vocaster Two → Mac/OBS | +80 ms | Da validare sulla Facecam 4K |
| Blue Yeti → Mac/OBS | 0 ms | Da validare sulla Facecam 4K |

In Advanced Audio Properties:

| Source | Sync Offset |
|---|---:|
| RØDE PodMic | 80 ms |
| Blue Yeti | 0 ms |
| VIDEO | 0 ms |

# 4. Blue Yeti — OBS source

## 4.1 Source Properties

| Parameter name | Current value |
|---|---|
| Device | Yeti Stereo Microphone |
| Enable Downmixing | On |

## 4.2 Filter order

1. Noise Suppression
2. Noise Gate
3. TDR VOS SlickEQ — Off
4. TDR Nova GE
5. TDR Kotelnikov
6. Limiter
7. Wider — Off

## 4.3 Noise Gate

| Parameter name | Current value |
|---|---:|
| Close Threshold | -42.00 dB |
| Open Threshold | -38.00 dB |
| Attack Time | 10 ms |
| Hold Time | 120 ms |
| Release Time | 180 ms |

## 4.4 TDR VOS SlickEQ

**Status:** Off.

The screenshot shows a possible configuration, but it is not part of the active Production chain. TDR Nova GE performs the principal EQ work.

## 4.5 TDR Nova GE — Blue Yeti

### Global

| Parameter name | Current value |
|---|---|
| Output Gain | 0.0 dB |
| Dry Mix | 0.0% |

### High-pass filter

| Parameter name | Current value |
|---|---:|
| HP Frequency | 68 Hz |
| HP Slope | 24 dB/oct |

### Band I

| Parameter name | Current value |
|---|---:|
| Filter Type | Low Shelf |
| Frequency | 120 Hz |
| Q | 0.70 |
| Gain | +1.5 dB |
| Dynamic processing | Off |

### Band II

| Parameter name | Current value |
|---|---:|
| Filter Type | Bell |
| Frequency | 300 Hz |
| Q | 1.20 |
| Gain | -2.0 dB |
| Dynamic processing | Off |

### Band III

| Parameter name | Current value |
|---|---:|
| Filter Type | Bell |
| Frequency | 900 Hz |
| Q | 1.20 |
| Gain | -2.0 dB |
| Threshold | -30 dB |
| Ratio | 2:1 |
| Attack | 10 ms |
| Release | 120 ms |
| Dynamic processing | On |

### Band IV

| Parameter name | Current value |
|---|---:|
| Filter Type | Bell |
| Frequency | 2500 Hz |
| Q | 1.50 |
| Gain | -2.0 dB |
| Dynamic processing | Off |

### Band V — de-esser

| Parameter name | Current value |
|---|---:|
| Frequency | 6.5 kHz |
| Q | 3.50 |
| Gain | 0.0 dB |
| Threshold | -24.0 dB |
| Ratio | 4.0:1 |
| Attack | 1 ms |
| Release | 80 ms |
| Dynamic processing | On |

### Band VI

| Parameter name | Current value |
|---|---:|
| Filter Type | High Shelf |
| Frequency | 10.0 kHz |
| Q | 1.07 |
| Gain | 0.0 dB |
| Dynamic processing | Off |

## 4.6 TDR Kotelnikov — Blue Yeti

| Parameter name | Current value |
|---|---:|
| Threshold | -31.0 dB |
| Peak Crest | 3.0 dB |
| Soft Knee | 2.0 dB |
| Ratio | 3.0:1 |
| Attack | 18 ms |
| Release Peak | 130 ms |
| Release RMS | 250 ms |
| Makeup | 0.0 dB |
| Dry Mix | Off |
| Out Gain | +3.0 dB |
| Low Freq Relax Frequency | 100 Hz |
| Low Freq Relax Slope | 3 dB/oct |
| Stereo Sensitivity Diff | 80% |

## 4.7 Limiter — Blue Yeti

| Parameter name | Current value |
|---|---:|
| Threshold | -1.00 dB |
| Release | 100 ms |

## 4.8 Wider — Blue Yeti

| Parameter name | Current value |
|---|---|
| Filter state | Off |
| Mono | On in the saved interface state |
| Width display | 24% |

# 5. RØDE PodMic — OBS source

## 5.1 Source Properties

| Parameter name | Current value |
|---|---|
| Device | Vocaster Two USB |
| Enable Downmixing | On |

## 5.2 Filter order

1. Noise Suppression
2. Noise Gate
3. TDR VOS SlickEQ — Off
4. TDR Nova GE
5. TDR Kotelnikov
6. Limiter
7. Wider — Off

## 5.3 Noise Suppression

| Parameter name | Current value |
|---|---|
| Method | RNNoise (good quality, more CPU usage) |

## 5.4 Noise Gate

| Parameter name | Current value |
|---|---:|
| Close Threshold | -42.00 dB |
| Open Threshold | -38.00 dB |
| Attack Time | 10 ms |
| Hold Time | 120 ms |
| Release Time | 180 ms |

## 5.5 TDR VOS SlickEQ

**Status:** Off.

## 5.6 TDR Nova GE — PodMic

### High-pass filter

| Parameter name | Current value |
|---|---:|
| HP Frequency | 80 Hz |
| HP Slope | 24 dB/oct |

### Band I

| Parameter name | Current value |
|---|---:|
| Filter Type | Low Shelf |
| Frequency | 120 Hz |
| Q | 0.70 |
| Gain | +1.5 dB |
| Dynamic processing | Off |

### Band II

| Parameter name | Current value |
|---|---:|
| Filter Type | Bell |
| Frequency | 350 Hz |
| Q | 1.10 |
| Gain | -1.5 dB |
| Dynamic processing | Off |

### Band III

| Parameter name | Current value |
|---|---:|
| Filter Type | Bell |
| Frequency | 900 Hz |
| Q | 1.20 |
| Gain | -2.0 dB |
| Threshold | -30.0 dB |
| Ratio | 2.0:1 |
| Attack | 10 ms |
| Release | 120 ms |
| Dynamic processing | On |

### Band IV

| Parameter name | Current value |
|---|---:|
| Filter Type | Bell |
| Frequency | 2.8 kHz |
| Q | 1.40 |
| Gain | -2.0 dB |
| Dynamic processing | Off |

**Evidence note:** `Dynamic processing = Off` is inferred from the inactive THRES state and the greyed dynamic controls in the screenshot.

### Band V — de-esser

| Parameter name | Current value |
|---|---:|
| Frequency | 7.0 kHz |
| Q | 3.00 |
| Gain | 0.0 dB |
| Threshold | -24.0 dB |
| Ratio | 3.5:1 |
| Attack | 1 ms |
| Release | 80 ms |
| Dynamic processing | On |

### Band VI

| Parameter name | Current value |
|---|---:|
| Filter Type | High Shelf |
| Frequency | 10.0 kHz |
| Q | 0.70 |
| Gain | +0.8 dB |
| Dynamic processing | Off |

## 5.7 TDR Kotelnikov — PodMic

| Parameter name | Current value |
|---|---:|
| Threshold | -23 dB |
| Peak Crest | 3 dB |
| Soft Knee | 3 dB |
| Ratio | 3:1 |
| Attack | 16 ms |
| Release Peak | 150 ms |
| Release RMS | 300 ms |
| Makeup | 0 dB |
| Dry Mix | Off |
| Out Gain | +5 dB |
| Low Freq Relax Frequency | 100 Hz |
| Low Freq Relax Slope | 3 dB/oct |
| Stereo Sensitivity Diff | 80% |

## 5.8 Limiter — PodMic

| Parameter name | Current value |
|---|---:|
| Threshold | -1.00 dB |
| Release | 60 ms |

## 5.9 Wider — PodMic

| Parameter name | Current value |
|---|---|
| Filter state | Off |
| Mono | On in the saved interface state |
| Width display | 24% |

# 6. VIDEO / BlackHole source

## 6.1 Sidechain compressor

| Parameter name | Current value |
|---|---:|
| Ratio | 6.10:1 |
| Threshold | -30.00 dB |
| Attack | 5 ms |
| Release | 200 ms |
| Output Gain | 0.00 dB |
| Sidechain/Ducking Source | RØDE PodMic |

# 7. Focusrite Vocaster Hub

## 7.1 Device and system

| Parameter name | Current value |
|---|---|
| Device | Vocaster Two |
| Sample Rate | 48 kHz |
| Firmware version | 1.7.0 |
| Phantom Power 48V | Off |

## 7.2 Host microphone channel

| Parameter name | Current value |
|---|---|
| Enhance | On |
| Enhance preset | Radio |
| Rumble Reduction | High |
| Auto Gain current control state | Default |
| Mic gain origin | Set using Auto Gain calibration |
| Fixed numeric gain | Not exposed in the available screenshot |

### Interpretation
Auto Gain was used to set the PodMic level. The current production gain is the result of that calibration; it is not documented as a precise numeric value in the available screenshot.

## 7.3 Guest channel

| Parameter name | Current value |
|---|---|
| Phantom Power 48V | Off |
| Enhance | Off / not part of the current production voice chain |
| Auto Gain | Default |

# 8. Sony ZV-E10 MK2

## 8.1 Video and recording

| Parameter name | Current value |
|---|---|
| File Format | XAVC S 4K |
| Record Setting | 25p, 60M, 4:2:0 8-bit |
| Shutter Speed | 1/50 |
| Aperture | f/4 |
| ISO | 640 |
| White Balance | AWB |
| Focus Mode | AF-C |
| Picture Profile | Off |
| Log Shooting | Off |
| PAL/NTSC Selector | PAL |
| Auto Power OFF Temp. | High |
| Power Save | Off |

## 8.2 HDMI output

| Parameter name | Current value |
|---|---|
| HDMI Resolution | 2160p |
| Output Resolution | 2160p |
| HDMI Info Display | Off |
| Rec. Media During HDMI Output | On |
| Effective HDMI signal to 4K X | 3840×2160, 50 fps |

### Operational rationale
Simultaneous SD recording is intentionally enabled. The Sony therefore remains the master/failback recording device while OBS receives the HDMI feed.

# 9. Elgato Game Capture 4K X

## 9.1 Elgato Capture Device Utility

| Parameter name | Current value |
|---|---|
| Capture Device | Elgato 4K X |
| Utility version | 1.3.1.684 |
| MCU / Firmware | 25.02.10 |
| Audio Input | HDMI Audio |
| HDMI Color Range | Bypass (same as input) |
| Input EDID Mode | Internal |
| HDR Tonemapping | Off |
| USB 10 Gbps | On |

## 9.2 OBS source properties

| Parameter name | Current value |
|---|---|
| Device | Elgato 4K X |
| Input format | 3840×2160, 50 fps, NV12 |
| FPS selection | Simple FPS Values |
| FPS | 50 |
| Buffering | Disabled / production configuration |
| OBS canvas/output | 1920×1080, 25 fps |

## 9.3 Future test — not Production

The analog audio input of the 4K X has not yet been validated. It must remain classified as `Experimental / Future test`, not as part of the current production pipeline.

# 10. Elgato Facecam 4K

## 10.1 Device and connection

| Parameter name | Current value |
|---|---|
| Device | Elgato Facecam 4K |
| Role | Webcam secondaria / camera alternativa ad alta risoluzione |
| Status | Production |
| Replaces | Logitech StreamCam, dismessa |
| Connection | Direct to MacBook Pro M3 Pro |
| Cable | Elgato USB-C cable, 5 Gbps bandwidth |
| Optical filter thread | 49 mm |
| Notes | La Facecam 4K non passa dal CalDigit; resta una sorgente video diretta al Mac, come già avveniva per la precedente StreamCam. |

## 10.2 Optical filter kit — Facecam 4K

| Filter / accessory | Size | Purpose / note | Status |
|---|---:|---|---|
| K&F Concept Black Diffusion 1/8 | 49 mm | Diffusione leggera per ammorbidire l'immagine in alcune condizioni di ripresa. | Available |
| HOYA UXII UV with Hoya Anti-Reflection Multi Coating | 49 mm | Filtro UV/protezione con trattamento antiriflesso. | Available |
| K&F Concept CPL Nano-Klear polarizer, 18-layer nano coating | 49 mm | Filtro polarizzatore per gestire riflessi e resa in situazioni specifiche. | Available |
| Lens cap | 49 mm | Protezione dell'obiettivo quando la Facecam 4K non viene usata per lunghi periodi. | Available |

## 10.3 Camera Hub — Production baseline (2026-10-01)

| Parameter name | Current value |
|---|---|
| Input | Elgato Facecam 4K |
| Format | 1080p30 (YUY2 raw) |
| Zoom / FOV | 174% |
| Pan / Tilt | 0% / 0% |
| Preset | A |
| Contrast | 55% |
| Saturation | 60% |
| Sharpness | 45% |
| Exposure | Manual |
| Shutter Speed | 1/33 s |
| ISO | 2851 |
| Dynamic Range | Standard |
| White Balance | Manual |
| Temperature | 4900 K |
| Tint | -3 |
| Noise Reduction | Custom |
| 2D Noise Reduction | 35 |
| 3D Noise Reduction | 34 |
| Anti-flicker | 50 Hz |

### Device details

| Parameter name | Current value |
|---|---|
| Firmware Version | 2.49.0000 (IQ: 1.10.00.26) |
| Low-Light Mode | Off (Recommended) |
| Status LED | Always on |
| LED Brightness | Near maximum |

### Evidence screenshots

- `screenshots/source-extracts/Settaggi_Facecam_4k_di_massima_001.png`
- `screenshots/source-extracts/Settaggi_Facecam_4k_di_massima_002.png`
- `screenshots/source-extracts/Settaggi_Facecam_4k_di_massima_003.png`

## 10.4 Retired webcam — Logitech StreamCam

| Parameter name | Historical value |
|---|---|
| Device | Logitech StreamCam |
| Status | Retired / dismessa |
| Previous role | Webcam secondaria / backup / fast workflow |
| Previous connection | Direct to MacBook Pro |
| Previous software | Logi Tune |

The following Logi Tune values are historical only and must not be treated as current Production settings:

| Parameter name | Historical value |
|---|---|
| HDR | Off |
| Anti-flicker | PAL 50Hz |
| Auto Focus | On |
| Auto Exposure | Off |
| Exposure | 903 |
| Gain | 90 |
| Auto White Balance | Off |
| Temperature | 5200 K |
| Brightness | 155 |
| Contrast | 120 |
| Saturation | 120 |
| Sharpness | 112 |

# 11. Lighting

| Device | Parameter | Current value |
|---|---|---|
| Neewer FS150B | Brightness | 36% |
| Neewer FS150B | Colour temperature | 5600 K |
| Elgato Key Light Air Left | Brightness | 50% |
| Elgato Key Light Air Left | Colour temperature | 5400 K |
| Elgato Key Light Air Right | Brightness | 35% |
| Elgato Key Light Air Right | Colour temperature | 5400 K |
| Bookshelf lamp | Brightness | 100% |
| Bookshelf lamp | Lampshade split | 40/60 |

**Orientation convention:** Left/Right are from Salvatore's seated point of view. The Right Key Light is the unit visible reflected in the glass cabinet behind him.

**Evidence screenshot:** `screenshots/source-extracts/Elgato_Key_Light_Air_Control_Center_2026-10-01.png`

# 12. Production workflows

## 12.1 Important recording

`PodMic → Vocaster Two → Sony camera input → Sony SD master`

Parallel backup/regia:

`PodMic → Vocaster Two USB → OBS`

Video:

`Sony HDMI → Elgato 4K X → Mac/OBS`

## 12.2 Fast workflow

`Blue Yeti → CalDigit TS5 Plus → Mac/OBS`

Typically paired with:

`Elgato Facecam 4K → Elgato USB-C 5 Gbps → MacBook Pro M3 Pro → OBS`

## 12.3 Active microphone rule

- Fast work: Blue Yeti active, PodMic muted.
- Serious work: PodMic active, Blue Yeti muted.
- Never leave both main voice microphones active together.

# 13. Known caveats

## 13.1 Capture-device reinitialization

When the 4K X source opens black or appears reset:

1. Right-click the existing Elgato source.
2. Select `Deactivate`.
3. Wait approximately 2 seconds.
4. Select `Activate`.

Use `Add Existing` when reusing the same capture device in another scene. Do not create multiple independent capture sources pointing to the same hardware.

## 13.2 Facecam 4K validation

The Elgato Facecam 4K Camera Hub parameters are baselined as Production as of 2026-10-01. A/V sync offsets remain to be validated.

## 13.3 Historical StreamCam wake-up exposure issue

This issue is historical only. Logi Tune could initially show the retired StreamCam image as too dark until the Exposure control was touched.

## 13.4 Sync playback validation

Do not use AirPlay, HomePod or Wi-Fi speakers to judge recorded A/V sync. Use local Mac speakers or wired headphones.

# 14. Experimental and future items

| Item | Status |
|---|---|
| Vocaster Rumble Reduction A/B test: High vs Low | Optional future test |
| Elgato 4K X analog audio input | Experimental / not yet tested |
| Fine sync test at +100 ms for PodMic | Not adopted; Production remains +80 ms |
| SlickEQ reactivation | Not adopted |
| Wider activation | Not adopted |
| 4K delivery from OBS | Not required in current workflow |
| Elgato Facecam 4K sync offset matrix | To be validated |
| Logitech StreamCam | Retired / historical only |

# 15. Mobile / off-studio audio kit

## 15.1 DJI Wireless Mic 3

| Component | Quantity | Role / note | Status |
|---|---:|---|---|
| DJI Wireless Mic 3 receiver RX | 1 | Receiver usable with iPhone USB-C and Sony ZV-E10 MK2. | Available |
| DJI Wireless Mic 3 transmitters TX | 2 | Wearable transmitters with magnetic clips, useful for presenter/interview/workshop capture. | Available |
| Deadcat windshields | 4 | Wind protection for mobile/off-studio use. | Available |

### Intended use

The DJI Wireless Mic 3 kit is intended for reliable audio capture outside the home studio, including workshops, seminars, university rooms, meeting rooms and similar environments. It complements the fixed studio chains based on Blue Yeti or RØDE PodMic + Vocaster Two.

# 16. Elgato Prompter navigation controller

## 16.1 Norwii N95 Bluetooth clicker

| Parameter name | Current value |
|---|---|
| Device | Norwii N95 Bluetooth clicker |
| Companion app | Norwii Presenter |
| Role | Remote chapter navigation for Elgato Prompter texts |
| Configuration | Buttons remapped to Elgato Prompter keyboard shortcuts |
| Use case | Navigate between chapters while reading during a recording or live session |

### Operational rationale

The Norwii N95 reduces the need to touch keyboard or mouse while reading from the Elgato Prompter. It supports chapter-to-chapter navigation during recordings and live sessions, improving Prompter usability and reducing interruption of delivery flow.

# 17. Source hierarchy


1. This file is the current single source of truth.
2. The split documents under `docs/` are navigational views of the same baseline.
3. Screenshots and source DOCX files are evidence.
4. Historical discussions and alternatives do not override Production values unless this file is explicitly updated.
