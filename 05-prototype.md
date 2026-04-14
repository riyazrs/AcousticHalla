# 05 Prototype & Design Specs

## Features
1. **Ruggedized Capacitive Interface:** 5 giant touch-sensitive pads built from bite-resistant polycarbonate, capable of withstanding 500kg of force.
2. **Dynamic Reward Dispenser:** Micro-dosing pump system that sprays novel scents/flavors (e.g., lime extract) onto high-fiber treats when specific musical sequences are played.
3. **Bio-Acoustic Engine:** Onboard synthesizer that generates species-specific soothing frequencies (avoiding high pitches that irritate certain mammals).
4. **Cloud Dashboard (The "Sanctuary Portal"):** Real-time data visualization showing animal engagement hours, predicted mood state, and hardware battery life.

## Architecture
- **Edge Device:** Solar-powered ESP32 microcontrollers handling touch inputs and local sound synthesis.
- **Connectivity:** LoRaWAN network to transmit data from remote sanctuary enclosures to a central hub.
- **Cloud Backend:** AWS IoT Core routing data to a Python (FastAPI) backend.
- **Frontend:** React-based dashboard for veterinary staff.

## User Flows
1. **Animal Flow:** Approaches pod -> Smells faint lime scent -> Touches pad -> Hears pleasant chime & receives lime-infused bamboo -> Touches another pad -> Hears harmonic chord.
2. **Zoologist Flow:** Logs into Dashboard -> Views "Engagement Heatmap" for Panda Enclosure A -> Notes a 40% reduction in pacing behavior -> Exports PDF report for annual welfare audit.

## Brand Guidelines
- **Primary Color:** Canopy Green (`#1E392A`) - Represents nature and sanctuary.
- **Accent Color:** Bio-Lime (`#D4FF00`) - Represents the novel, energetic spark of cognitive engagement.
- **Typography:** *Inter* (Clean, scientific, highly legible for dashboard data) and *Playfair Display* (for high-end B2B marketing headers).
- **Tone:** Scientific, Empathetic, Cutting-Edge.

## MVP Development Timeline (12 Weeks)
- **Weeks 1-3:** Hardware casing fabrication and capacitive touch calibration (stress-testing with heavy weights).
- **Weeks 4-6:** Edge software development (sound synthesis logic and dispenser integration).
- **Weeks 7-9:** Cloud infrastructure setup and React dashboard wireframing.
- **Weeks 10-12:** Closed beta field-testing at a local partnered zoo; data collection and algorithm tweaking.