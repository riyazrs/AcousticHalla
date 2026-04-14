# 05 Prototype & Design Specs — v2.0

## Features

1. **Ruggedized Capacitive Interface:** 5 giant touch-sensitive pads (C4–G4) built from bite-resistant polycarbonate, capable of withstanding 500 kg of force. Each pad emits a species-soothing triangle-wave tone with a reverb tail on interaction.

2. **Dynamic Reward Dispenser — Unit RD-1:** A three-phase micro-dosing pump system (PRESSURIZING → DISPENSING → IDLE) that sprays lime-extract scent onto high-fibre treats when a 4-pad cognitive sequence is completed. Dispensing is signalled visually via nozzle LED, on-unit screen, animated lime particle burst (22 particles in a 110° spray cone), mist cloud, and a status banner.

3. **Cognitive Sequence Tracker:** A 4-step progress indicator that fills one bar per pad interaction, communicating remaining steps to the reward and resetting on each dispense cycle.

4. **Bio-Acoustic Engine:** Web Audio API oscillator bank (triangle wave, 261–392 Hz) with a delay-feedback reverb tail (28 ms delay, 0.22 feedback gain). On successful sequence completion a C-major ascending arpeggio (C5 → E5 → G5 → C6) confirms the reward event.

5. **Adaptive Scale Shifting:** AI log milestones at 10, 20, and 30 interactions automatically shift the displayed harmonic scale (C-Major → G-Major Pentatonic → D Dorian → A Mixolydian) to simulate the edge-AI habituation-prevention algorithm.

6. **Cloud Analytics Dashboard (Sanctuary Portal):** Real-time metrics for Neuroplastic Engagement and Estimated Cortisol Reduction, animated bar graphs, Active Harmonic Scale, Total Interactions, and a timestamped System Log showing pad events, AI decisions, dispenser phases, and CV sensor outputs.

7. **Panda Behavioural State Tracker:** CV-sensor-simulated panda state displayed in the header (IDLE → CURIOUS → ENGAGED → ACTIVE → STIMULATED → CALM POST-REWARD), updating automatically with a log entry on each state transition.

---

## Architecture

### Web Prototype (Alpha)

| Layer | Technology | Purpose |
|---|---|---|
| UI / Interaction | Vanilla HTML5 / CSS3 / JavaScript (ES6+) | 3-panel layout: Touch Interface, Dispenser Unit, Analytics |
| Audio Engine | Web Audio API — OscillatorNode, GainNode, DelayNode | Triangle-wave tones, delay-feedback reverb, reward arpeggio |
| Animation | CSS keyframe animations + JS DOM injection | Particle spray (22 particles), mist cloud, pad ripple, LED pulse |
| State Machine | JS state variables | Dispenser phases, sequence tracker, scale index, panda state |
| Fonts | Google Fonts — Inter + JetBrains Mono | Scientific dashboard aesthetic |

### Production System (Hardware Target)

| Layer | Technology | Purpose |
|---|---|---|
| Edge Device | Solar-powered ESP32 microcontroller | Capacitive touch sensing, local audio synthesis, dispenser control |
| Connectivity | LoRaWAN (low-power wide-area) | Transmits interaction data from remote enclosures to central hub |
| Reward Hardware | Micro-dosing peristaltic pump + solenoid valve | Precise lime-extract dispensing on sequence completion |
| Biometric Sensing | Computer Vision (CV) camera + IR sensors | Detects animal proximity, dwell time, and behavioural state |
| Cloud Backend | AWS IoT Core → Python FastAPI | Routes edge telemetry; runs engagement and cortisol-reduction models |
| Frontend Dashboard | React (TypeScript) | Real-time behavioural analytics and welfare compliance reports |
| Privacy Layer | Edge-based face-blurring (OpenCV) | GDPR/DPIA compliance — anonymises staff and visitor images at source |

---

## User Flows

### Animal Flow (Simulated in Prototype)
1. Animal approaches pod — detects faint lime scent from primed dispenser nozzle
2. Touches Pad 1 → hears soothing C4 tone; sequence dot 1/4 fills
3. Touches Pads 2, 3, 4 → harmonics build; all 4 dots fill
4. Dispenser RD-1 enters PRESSURIZING phase (orange LED, screen alert)
5. DISPENSING phase: nozzle tip glows lime, 22 particles burst upward, mist cloud expands, reward chime plays, lime treat dispensed
6. Panda state advances (CURIOUS → ENGAGED → ACTIVE)
7. Cycle resets; dispenser returns to IDLE

### Zoologist Flow (Dashboard)
1. Logs into Sanctuary Portal
2. Views Neuroplastic Engagement score climbing in real time
3. Monitors Estimated Cortisol Reduction trend
4. Reads System Log: confirms dispenser cycles, scale shifts, CV detections
5. Exports compliance report for annual welfare audit

---

## Dispenser Phase State Machine

```
[IDLE] ──── sequence complete ────► [PRESSURIZING] (650 ms)
                                            │
                                    ▼
                               [DISPENSING] (2 500 ms)
                               · Nozzle LED on
                               · Particle burst (22 particles)
                               · Mist cloud animation
                               · Reward chime (C5–C6 arpeggio)
                               · Banner notification
                                            │
                                    ▼
                                 [IDLE]
```

---

## Brand Guidelines

- **Primary Colour:** Canopy Green `#1E392A` — nature and sanctuary
- **Accent Colour:** Bio-Lime `#D4FF00` — cognitive spark, reward signal
- **Background:** Deep Forest `#07100a`
- **Card Surface:** `#0f1c13`
- **Typography:** *Inter* (UI, metrics), *JetBrains Mono* (dashboard, log, hardware screen)
- **Tone:** Scientific · Empathetic · Cutting-Edge

---

## MVP Development Timeline (12 Weeks)

| Weeks | Milestone |
|---|---|
| 1–3 | Hardware casing fabrication; capacitive pad calibration and panda-force stress-testing (≥500 kg) |
| 4–6 | Edge firmware — sound synthesis, dispenser pump control, LoRaWAN telemetry |
| 7–9 | AWS IoT Core pipeline; FastAPI backend; React dashboard MVP |
| 10–12 | Closed beta at partnered zoo; behavioural data collection; edge-AI algorithm calibration |
| Post-MVP | GDPR DPIA completion; edge face-blurring integration; regulatory sign-off |
