# JE-Hackathon

# Lloyd Reflect 🚗✨  
### AI-powered driver risk reflection for safer, more responsible mobility

Lloyd Reflect is a prototype built for **Hack For Good 4.0 – Lloyd Assurance**.  
It combines **smartphone sensors**, **phone camera**, and **OBD-II vehicle data** to provide a **real-time driver risk score**, detect **distraction / fatigue**, and encourage **responsible, eco-friendly driving**.

> **Goal:** Help Lloyd Assurance move from *reactive* claim management to *proactive* risk prevention and market domination in car insurance in Tunisia.

---

## 🌍 Context & RSE Vision

Road accidents in Tunisia are strongly linked to:
- Driver **fatigue** and **distraction** (smartphone, inattention)
- Poor vehicle maintenance
- Lack of real-time feedback to drivers

At the same time, insurers lack:
- High-quality **behavioral data**
- Tools to **encourage safer habits** in a way that is accessible and low-cost

**Lloyd Reflect** sits at the intersection of:
- **RSE** (road safety, inclusion, eco-driving)
- **IA** (real-time detection, scoring, insights)
- **Insurance innovation** (behavior-based risk models)

---

## 🎯 Problem Statement

1. Drivers have **no live visibility** on how risky their driving is at a given moment.  
2. Existing telematics devices are **expensive**, **intrusive**, or limited to high-end vehicles.  
3. Insurers like Lloyd need **better predictive signals** to:
   - Reduce accidents
   - Personalize pricing fairly
   - Promote a culture of **responsible mobility**

---

## 💡 Our Solution — Lloyd Reflect

**Lloyd Reflect** turns:
- A **smartphone**, and  
- A low-cost **OBD-II dongle**  

into a **real-time safety co-pilot**.

### Core Ideas

- **Reflect risk, don’t just record it** → show drivers a simple, understandable **risk score**.
- Combine **driver behavior** (camera + motion) with **vehicle state** (OBD data).
- Run intelligence **on-device** for **privacy** and low friction.

---

## 🔧 Key Features (Phase 1 MVP)

### 1. Real-time Driver State Detection (Phone Camera + Sensors)
- Live camera view focused on the driver
- Simple labels:
  - `Attentive`
  - `Distracted`
  - `Drowsy`
- Uses basic rule-based logic (Phase 1) on:
  - Head orientation
  - Eye closure duration
  - Sudden phone/vehicle movements

### 2. Dynamic Risk Score (0–100)
- Single numeric score updated in real time:
  - Starts low when driving is stable and attentive
  - Increases when distraction, fatigue, or harsh events occur
  - Decreases gradually during stable, attentive driving
- Designed to be:
  - **Simple** for drivers
  - **Actionable** for insurers and fleets

### 3. Alerts & Feedback
- Phone vibration + short warning message:
  - `"Distraction detected — slow down."`
  - `"Fatigue risk — take a break."`
- Non-intrusive and configurable

### 4. OBD-II Integration (Vehicle Data)
Using a standard **Bluetooth OBD-II dongle**, Lloyd Reflect reads:
- Vehicle **speed**
- Engine state (e.g. check-engine light)
- RPM / basic telemetry (as available)

This allows:
- Contextualization of risk (e.g. distraction at 20 km/h vs 110 km/h)
- Early detection of **maintenance issues**
- Building advanced risk models for Lloyd in later phases

> Phase 1: basic integration and display of key OBD values.  
> Later phases: more advanced predictive maintenance & risk modeling.

### 5. Privacy by Design
- Detection is performed **locally on the device** (no raw video upload by default).
- Only **aggregated / anonymized** scores or events are shared if the user consents.
- Aligns with RSE principles of **digital responsibility and trust**.

---

## 🧠 Where AI Comes In

**Phase 1 (Hackathon MVP):**
- Hybrid approach:
  - Rule-based logic (thresholds, timers) for distraction/fatigue detection
  - Sensor fusion for risk scoring
- IA used as:
  - A framework for **behaviour modeling**, **scoring**, and future learning
  - A way to illustrate what can be improved with data from pilots

**Future Phases:**
- Computer vision models (on-device) for:
  - Eye tracking
  - Blink rate
  - Head pose estimation
- Time-series models on OBD + phone data for:
  - Driver “signature”
  - Crash risk prediction
  - Eco-driving and emissions estimation

---

## 🏛 Architecture (High-Level)

```text
Smartphone
 ├─ Camera stream  ──► Driver State Module (Attentive / Distracted / Drowsy)
 ├─ Motion sensors ──► Event Detector (harsh braking / acceleration / phone handling)
 ├─ Bluetooth OBD  ──► Vehicle Data (speed, engine status, RPM)
 └─ Risk Engine    ──► Risk Score (0–100) + Alerts

Optional
 └─ Cloud / API    ──► Aggregated data for Lloyd dashboards & analytics
