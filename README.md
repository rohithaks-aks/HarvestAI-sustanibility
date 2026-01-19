# HarvestAI: Universal E-Waste Intelligence Agent (v2.0)

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Tech Stack](https://img.shields.io/badge/AI-TensorFlow.js-orange)
![SDG Alignment](https://img.shields.io/badge/SDG-12%20Responsible%20Consumption-blue)
![License](https://img.shields.io/badge/license-MIT-green)

> **"Turning Electronic Waste into Educational Gold."**

## 📖 Project Overview
**HarvestAI v2** is a browser-based, **Human-in-the-Loop AI Agent** designed to solve the growing crisis of university electronic waste. Unlike static identification tools, HarvestAI uses a hybrid architecture combining **Computer Vision** (Edge AI) with **Real-Time Knowledge Retrieval** (RAG via Wikipedia API) to identify, diagnose, and repurpose *any* electronic component.

The system empowers students to safely salvage "junk" components, bridging the gap between resource scarcity and hands-on engineering education.

---

## 🚀 Key Features (v2.0 Upgrade)

### 1. 👁️ Hybrid Computer Vision
* **Edge-Based Detection:** Uses a custom MobileNet model (via Teachable Machine) running entirely in the browser using TensorFlow.js.
* **Privacy First:** No images are sent to the cloud; all vision processing happens locally.

### 2. 🧠 Unlimited Knowledge Agent (RAG)
* **Dynamic Retrieval:** Integrates the **Wikipedia REST API** to fetch live definitions for recognized parts.
* **Fallback Search:** Includes a "Manual Input" mode that allows the agent to research components it was never trained on visually.

### 3. 🛡️ AI Safety Engine
* **Heuristic Analysis:** Automatically scans retrieved text for danger keywords (e.g., "Lithium," "High Voltage," "Toxic") and issues immediate safety warnings.
* **Voice Guidance:** Built-in Text-to-Speech (TTS) for accessibility in busy lab environments.

### 4. 🌍 Sustainability Gamification
* **Impact Tracking:** Real-time dashboard tracks "E-Waste Diverted" (in grams) and "CO₂ Emissions Prevented."
* **Smart Deep Search:** Generates context-aware search queries to find 2026-era upcycling projects on Hackster.io and Instructables.

---

## 🛠️ Technical Architecture



[Image of software architecture diagram]


The application follows a **Client-Side Agentic Workflow**:

1.  **Input Layer:** Webcam Stream OR Text Input.
2.  **Perception Layer:** * *Vision:* MobileNet Classifier (Confidence Threshold > 0.95).
    * *Text:* Keyword Extraction.
3.  **Reasoning Layer (The Agent):**
    * Queries Wikipedia API for ground truth.
    * Runs Logic Rules for Safety Assessment.
4.  **Action Layer:**
    * Updates DOM (Glassmorphism UI).
    * Triggers Voice Synthesis.
    * Generates External Search Links.

---

## 💻 Tech Stack

* **Frontend:** HTML5, CSS3 (CSS Variables, Flexbox/Grid).
* **AI Engine:** TensorFlow.js, Google Teachable Machine.
* **API Integration:** Wikipedia REST API v1.
* **Deployment:** GitHub Pages / Vercel (Static Hosting).

---

## ⚙️ Installation & Setup

This project is designed to be lightweight and zero-dependency.

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/your-username/harvest-ai-v2.git](https://github.com/your-username/harvest-ai-v2.git)
    ```

2.  **Configure the Model:**
    * Open `index.html`.
    * Locate Line 160: `const URL = "..."`.
    * Replace with your trained Teachable Machine model URL.

3.  **Run:**
    * Simply double-click `index.html` to open in any modern browser (Chrome/Edge recommended).
    * *Note:* For webcam access, the file must be run on `localhost` or a secure HTTPS server (like GitHub Pages).

---

## 🎯 Sustainable Development Goals (SDG) Alignment

### Primary: SDG 12 (Responsible Consumption & Production)
* **Target 12.5:** Substantially reduce waste generation through prevention, reduction, recycling, and reuse.
* **Impact:** HarvestAI directly prevents functional electronics from entering landfills by giving them a second life.

### Secondary: SDG 4 (Quality Education)
* **Target 4.4:** Increase the number of youth and adults who have relevant skills for employment.
* **Impact:** Teaches students hardware debugging, datasheets reading, and reverse engineering.

---

## 🔮 Future Roadmap

* **v3.0:** Integration with **Google Gemini API** for generative circuit design based on available parts.
* **Cloud Database:** User login system to save "Digital Inventory" of rescued parts across devices.
* **Marketplace:** A "Campus Exchange" feature to trade rescued components between students.

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:
1.  Fork the repository.
2.  Create a feature branch (`git checkout -b feature/NewSensor`).
3.  Commit your changes.
4.  Open a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Built with ❤️ for the AI for Sustainability Internship 2026.*
