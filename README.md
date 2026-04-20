# 🛒 Mercari-Scraper: Intelligent Shopping Assistant
**Your Agentic Bridge to Mercari Japan**

[![Tested on Gemini](https://img.shields.io/badge/Tested_on-Gemini_CLI-8E44AD?style=for-the-badge&logo=google-gemini&logoColor=white)](https://github.com/google/gemini-cli)
[![Tech Stack: Python](https://img.shields.io/badge/Python-3.12+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![UI: Streamlit](https://img.shields.io/badge/UI-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

[![Live App](https://img.shields.io/badge/Live_App-Click_Here_to_Explore-blue?style=for-the-badge&logo=vercel)](https://mercari-scraper.streamlit.app/)

**Mercari-Scraper** is an agentic shopping assistant that understands natural language queries, performs real-time web scraping on Mercari Japan, and provides reasoned product recommendations without any third-party framework overhead.

## 🎬 Visual Preview
Since this is a backend-heavy agentic tool, here is the architectural layout of the **Streamlit Intelligent Interface**:

```mermaid
graph TD
    subgraph UI_Header [🛒 Mercari Japan Assistant]
        direction LR
        Logo[✨] --- Search[Search Bar: 'Nintendo Switch OLED'] --- Btn[Analyze Market]
    end
    
    subgraph Results_Area [Smart Recommendations]
        direction LR
        R1[<b>Product A</b><br/>5000 JPY<br/>Condition: Good]
        R2[<b>Product B</b><br/>4500 JPY<br/>Condition: Used]
        R3[<b>Product C</b><br/>6000 JPY<br/>Condition: Mint]
    end

    subgraph AI_Reasoning [Agent Insight Panel]
        Reason[<b>GPT-4o Analysis:</b><br/>'Product A is the winner because...']
    end

    UI_Header --> Results_Area
    Results_Area --> AI_Reasoning
```

`✅ Verified Demo | ✅ Secure API Handling | ✅ MIT Licensed | ✅ TDD-Verified`

## 🏗 Architecture
The project follows a modular agentic architecture, decoupling the UI from the scraping and reasoning engines.

```mermaid
graph TD
    A[Streamlit UI] --> B[Chat Assistant]
    B --> C[Mercari Scraper]
    B --> D[Product Ranker]
    B --> E[LLM Service]
    C --> F[(PostgreSQL)]
    D --> F
    E --> G[OpenAI GPT-4o]
```

### Core Components
- **Agent Engine (`core/`)**: Orchestrates the flow between user intent and tool execution using advanced function calling.
- **Data Layer (`backend/`)**: Advanced Selenium/BS4 engine for real-time extraction with PostgreSQL persistence.
- **Intelligence Hub**: Multi-criteria product ranking and multi-language support (English/Japanese).

## 🚀 Key Features
- 🤖 **Intelligent Agent**: Natural language query parsing and smart tool selection via GPT-4o.
- 🔍 **Real-time Scraping**: Direct, low-latency integration with Mercari Japan.
- 🎯 **Reasoned Recommendations**: Personalized suggestions with clear logical explanations.
- 📊 **Dynamic Dashboard**: Interactive Streamlit interface for exploring products and trends.

## 🛠 Technology Stack
- **Languages**: Python 3.12+ (Modern typing and hints)
- **Frameworks**: Streamlit (UI), SQLAlchemy (ORM)
- **AI/ML**: OpenAI GPT-4o, BS4/Selenium (Scraping)
- **Database**: PostgreSQL (Robust storage)
- **DevOps**: pytest (TDD), Streamlit Cloud (CI/CD)

## 📦 Getting Started

### Prerequisites
- Python 3.12+
- PostgreSQL
- OpenAI API Key

### Setup
1. **Clone & Install**:
   ```bash
   git clone https://github.com/ayushxx7/Mercari-Scraper.git
   cd Mercari-Scraper
   pip install -r requirements.txt
   ```

2. **Environment**:
   Create a `.env` file:
   ```env
   OPENAI_API_KEY=your_key
   DATABASE_URL=postgresql://user:password@localhost/mercari_db
   ```

3. **Run**:
   ```bash
   python -c "from core.database import DatabaseManager; db = DatabaseManager()"
   streamlit run app.py
   ```

## 🧪 Testing
```bash
pytest --cov=core --cov=app
```

## 📜 License
This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---
*Built with ❤️ for Mercari Japan Shopping Automation.*
