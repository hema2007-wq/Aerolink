# ✈️ AeroLink — Aviation Safety Intelligence

> **Predict. Explain. Protect.**

A production-grade, self-contained Agentic AI + Explainable AI Flight Safety Monitoring System — runs entirely in the browser, no backend required.

---

## Features

| Module | Description |
|---|---|
| **Digital Twin Engine** | Physics-based telemetry simulation with Gaussian noise and phase-accurate targets |
| **WebSocket Mock Layer** | 500ms tick rate via `TelemetryBus` — behaves like a live data stream |
| **Statistical Anomaly Detection** | Z-score analysis on a 60-tick rolling window per sensor channel |
| **Agentic AI Reasoning Loop** | 5-stage OBSERVE→ANALYZE→REASON→DECIDE→EXPLAIN pipeline |
| **Explainable AI Engine** | Feature importance, deviation table, counterfactual analysis, trend summary |
| **3D Aircraft Model** | Interactive Three.js model reacting to live pitch/roll/anomaly data |
| **Real-Time Dashboard** | Pastel aviation theme, sticky header, live alerts, phase tracker |

## Quick Start

```bash
npm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

## Architecture

```
src/
├── engine/
│   ├── TelemetryBus.js       # Digital twin + data pipeline orchestrator
│   ├── AnomalyDetector.js    # Z-score anomaly detection (rolling window)
│   ├── AgentLoop.js          # 5-stage agentic reasoning loop
│   └── XAIEngine.js          # Explainability engine
├── context/
│   └── TelemetryContext.jsx  # Global React state (500ms live feed)
└── components/
    ├── Header.jsx             # Masthead with LIVE indicator
    ├── FlightPhaseTracker.jsx # Takeoff→Climb→Cruise→Descent stepper
    ├── AircraftModel3D.jsx    # Three.js interactive aircraft
    ├── RiskIndicator.jsx      # Risk badge + confidence bar + action
    ├── TelemetryPanel.jsx     # 8-parameter live sensor grid
    ├── AlertFeed.jsx          # Scrollable alert event log
    └── XAIPanel.jsx           # Full explainability panel
```

## Flight Phases

| Phase | Duration | Altitude | Speed |
|---|---|---|---|
| Takeoff | 3 min | ~2,000 ft | ~140 kts |
| Climb | 9 min | ~28,000 ft | ~240 kts |
| Cruise | 23 min | ~35,000 ft | ~440 kts |
| Descent | 10 min | ~3,000 ft | ~220 kts |

Anomalies are stochastically injected (~5% probability per tick) across four fault types: engine instability, stall precursor, pitch-altitude mismatch, and fuel system anomaly.
