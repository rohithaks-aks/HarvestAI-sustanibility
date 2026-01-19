# HarvestAI: AI-Assisted E-Waste Decision Support System (v2.0)

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Tech Stack](https://img.shields.io/badge/AI-TensorFlow.js-orange)
![SDG Alignment](https://img.shields.io/badge/SDG-12%20Responsible%20Consumption-blue)
![License](https://img.shields.io/badge/license-MIT-green)

> Turning discarded electronics into safe learning opportunities.

---

## 📖 Project Overview

HarvestAI is a browser-based, **human-in-the-loop AI-assisted decision-support system** designed to reduce electronic waste on university campuses. The system helps users identify **common electronic components**, understand basic safety considerations, and explore responsible reuse or recycling options.

The project focuses on **responsible application of AI**, combining client-side computer vision with information retrieval to support sustainable decision-making without automating physical actions.

---

## 🚀 Key Features

### 1. 👁️ Client-Side Component Identification
- Uses a pre-trained image classification model (Teachable Machine + TensorFlow.js).
- Identifies a **limited, predefined set of common electronic components**.
- All inference runs locally in the browser to ensure privacy.

### 2. 🧠 Information Retrieval Support
- Retrieves high-level contextual information using the Wikipedia REST API.
- Manual input mode allows users to search for components not included in the visual model.
- Directs users to authoritative sources such as datasheets via web search.

### 3. 🛡️ Safety-Aware Decision Support
- Rule-based heuristics flag potential risks (e.g., batteries, capacitors).
- Displays handling warnings and encourages responsible disposal when necessary.
- Includes optional text-to-speech feedback for accessibility.

### 4. 🌍 Sustainability Awareness
- Tracks approximate indicators for e-waste diversion and environmental impact.
- Provides links to recycling centers and educational reuse resources.
- Metrics shown are **indicative only**, not precise lifecycle assessments.

---

## 🛠️ Technical Architecture

The application follows a **client-side decision-support workflow**:

1. Input via webcam or text
2. Image classification (limited dataset)
3. Information retrieval (Wikipedia API)
4. Rule-based safety checks
5. User guidance and external resource links

The system prioritizes transparency, safety, and human oversight.

---

## 💻 Tech Stack

- Frontend: HTML5, CSS3, JavaScript
- AI: TensorFlow.js, Google Teachable Machine
- APIs: Wikipedia REST API
- Deployment: Static hosting (GitHub Pages / Vercel)

---

## ⚙️ Installation & Setup

1. Clone the repository
2. Replace the Teachable Machine model URL in `index.html`
3. Open the project in a modern browser (HTTPS required for webcam)

No backend or data storage is used.

---

## 🎯 SDG Alignment

### SDG 12 – Responsible Consumption and Production
- Encourages reuse and responsible disposal of electronic components.
- Raises awareness of sustainable practices at the campus level.

### SDG 4 – Quality Education
- Supports hands-on learning by improving access to affordable components.
- Builds practical hardware literacy.

---

## 🔒 Responsible AI Disclaimer

This project is an **educational decision-support prototype**.
It does not replace expert judgment, certified recycling procedures, or professional safety training.
Users must follow institutional safety and disposal guidelines.

---

## 🔮 Future Scope

- Expansion of the component dataset
- Structured datasheet extraction
- Integration with institutional recycling systems

---
flowchart TD
    subgraph Client_Side_Browser ["🛡️ Client-Side Browser (Privacy Layer)"]
        User((Student)) -->|Shows Component| Cam[Webcam Input]
        User -->|Types Name| Manual[Manual Input]
        
        Cam -->|Video Stream| Vision[TensorFlow.js / MobileNet]
        Vision -->|Classifies| Confidence{Confidence > 95%?}
        
        Confidence -- No --> Loop[Wait / User Retry]
        Confidence -- Yes --> Agent[HarvestAI Logic Agent]
        Manual --> Agent
        
        subgraph Logic_Core ["🧠 Intelligence Core"]
            Agent -->|Request Info| WikiAPI[Wikipedia RAG]
            Agent -->|Analyze Text| Safety[⚠️ Safety Heuristics Engine]
            Agent -->|Update Stats| Impact[Gamification Counter]
        end
        
        Safety -->|Text-to-Speech| Voice[Voice Warning]
        WikiAPI -->|Context Data| UI[Display Result Card]
        Agent -->|Generate Link| Ext[External Search]
    end
    
    subgraph External_Web ["🌐 External World"]
        WikiAPI <-->|Fetch Data| WikipediaServer((Wikipedia API))
        Ext -->|User Clicks| Hackster((Project Repos))
    end
    
    classDef safe fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    classDef danger fill:#ffccbc,stroke:#bf360c,stroke-width:2px;
    classDef ai fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;
    
    class Vision,Agent,WikiAPI ai;
    class Safety danger;
    class Client_Side_Browser safe;

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

