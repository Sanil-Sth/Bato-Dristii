# Bato Dristi (बाटो दृष्टि)
### AI-Powered Road Hazard Intelligence System

Bato Dristi is a privacy-preserving, AI-powered road intelligence system that turns vehicle cameras into passive sensors — detecting, verifying, and prioritizing road hazards to help municipalities move from reactive to proactive road maintenance.

Built for **Frogtober**.

---

## 🚧 The Problem

Road maintenance today is almost entirely reactive:

```
Road damage appears → Citizen notices → Complaint filed →
Manual inspection → Maintenance decision → Repair
```

This means authorities often don't know about hazards until they've already gotten worse, manual inspection doesn't scale, and citizen reporting is inconsistent and duplicated.

**The real question:** how can a city continuously understand road conditions and prioritize maintenance — without a small army of inspectors manually checking every street?

## 💡 The Solution

Instead of sending dedicated workers out to inspect roads, Bato Dristi turns vehicles that are *already driving* — buses, taxis, delivery fleets, municipal vehicles — into a distributed road-condition sensing network.

```
Vehicle Camera / Dashcam
        ↓
Computer Vision AI (hazard detection)
        ↓
Privacy Processing & Anonymization
        ↓
GPS + Timestamp + Severity
        ↓
Hazard Database
        ↓
Duplicate Detection / Spatial Clustering
        ↓
Priority Intelligence Engine
        ↓
Municipality Dashboard → Prioritized Maintenance Action
```

The core idea: **Detection → Verification → Prioritization → Action.**

A single AI detection is just an observation, not a fact. When multiple independent vehicles flag the same location, confidence goes up — turning scattered raw detections into a *verified, ranked* maintenance queue instead of a noisy map of red dots.

##  What It Detects (MVP)

- **Potholes** (primary, reliable detection)
- Stretch goals: cracks, open manholes, debris, damaged road surfaces

##  Privacy by Design

Continuous vehicle footage could capture faces, license plates, homes, and movement patterns — so Bato Dristi is built to minimize data at the source rather than centrally store raw video:

```
Footage → AI processes locally → Hazard detected?
                                      ↓ yes
                        Extract relevant evidence
                                      ↓
                        Blur faces / plates
                                      ↓
                        Generate hazard metadata only
                                      ↓
                        Sync to server (no full video)
```

Only hazard type, GPS location, timestamp, confidence, severity, and (optionally) a small anonymized evidence image ever leave the vehicle.

##  Core Features

| Feature | Description |
|---|---|
| **Hazard Detection** | Computer vision model (YOLO) identifies potholes in road footage |
| **Geo-tagging** | Detections associated with GPS coordinates + timestamp |
| **Hazard Map** | Interactive map of detected hazards |
| **Clustering** | Groups repeated detections near the same location into one verified hazard |
| **Priority Scoring** | Ranks hazards by severity, verification frequency, persistence, and road importance |
| **Municipal Dashboard** | Converts raw detections into an actionable, prioritized maintenance list |

##  Tech Stack

- **AI / Computer Vision:** Python, YOLO, OpenCV
- **Backend:** FastAPI
- **Frontend:** React / Next.js, Tailwind CSS
- **Database:** PostgreSQL + PostGIS
- **Maps:** Leaflet
- **Architecture:** Edge AI / local-first processing

##  Project Structure

```
bato-dristi/
├── cv-model/        # YOLO training, inference, hazard detection
├── backend/         # FastAPI service, clustering & priority engine
├── frontend/        # Municipal dashboard (React/Next.js)
├── data/            # Sample road footage & annotated frames
└── README.md
```

##  Getting Started

```bash
# Clone the repo
git clone https://github.com/<your-username>/bato-dristi.git
cd bato-dristi

# Backend setup
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

# Frontend setup
cd ../frontend
npm install
npm run dev
```

##  Roadmap

- [ ] Phase 1 — MVP: hazard detection + map + basic clustering + priority score
- [ ] Phase 2 — Small pilot with a real fleet (taxi/bus/logistics)
- [ ] Phase 3 — Integration with fleet dashcams & management systems
- [ ] Phase 4 — Voluntary private vehicle participation

##  Frogtober

This project is being built for **Frogtober**.

---

**Bato Dristi** — giving roads the intelligence to be seen before hazards become bigger problems.
