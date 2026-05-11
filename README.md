# DSN-X-BCT-Data-AI-Summit-2026-
DSN X BCT Data &amp; AI Summit 2026 Hackathon Submission
# VeX AI: Hyper-Local Agentic Commerce Engine

**Submission for Bluechip x DSN Hackathon 2026**  
**Developed by:** Solomon Israel Maichibi (Vessels Versatilis LTD)

## 🚀 
VeX AI is built to satisfy both Task A and Task B from the hackathon brief:
- **Task A:** User modeling with tone, rating behavior, and contextual nuance.
- **Task B:** Personalized recommendation with cold-start handling and agentic reasoning.
- **Bonus:** Nigerian context detection for cultural fidelity.

## 🧠 Core System
- **FastAPI** web service for the API endpoint
- **LangChain + Gemini Pro** for agentic LLM reasoning
- **Docker** for containerization and reproducibility
- **Evaluation suite** for RMSE, Hit Rate, and NDCG metrics

## 📂 Included Files
- `main.py` — Task A / Task B API logic
- `agents.py` — Agentic workflow with cultural prompt injection
- `utils.py` — Nigerian context detection
- `eval.py` — Metric computation for Task A and Task B
- `Dockerfile` — Containerization for submission
- `README.md` — Reproduction instructions
- `solution_paper.md` — Technical write-up draft
- `Amazon_Reviews.csv` — Sample review dataset for testing

## 📦 Installation
```bash
cd c:/Users/Elite/Desktop/dssn
python -m pip install -r requirements.txt
```

## 🔧 Setup
Create a `.env` file in the project root with:
```env
GOOGLE_API_KEY=your_api_key
USE_MOCK=true
```
Use `USE_MOCK=true` while testing without API access.

## ▶️ Running the API
```bash
python main.py
```
Open `http://127.0.0.1:8000/docs` to explore the endpoints.

## 🧪 API Usage
### Task A
`POST /task-a/predict`

Request body:
```json
{
  "user_history": "I bought one blender last year, the thing just start to smoke after two weeks. Abeg, I need something that can handle this our light issue and still grind beans well well.",
  "new_item_metadata": "Heavy-Duty 1500W Industrial Blender with Surge Protection and Copper Motor."
}
```

### Task B
`POST /task-b/recommend`

Request body:
```json
{
  "user_history": "I usually avoid items with slow delivery, especially in Lagos.",
  "candidates": ["Item A", "Item B", "Item C"]
}
```

## 📈 Evaluation
Use `eval.py` to compute Task A and Task B metrics.

### Task A
```bash
python eval.py --task a --truth truth_task_a.csv --predictions predictions_task_a.csv
```

### Task B
```bash
python eval.py --task b --truth truth_task_b.csv --predictions predictions_task_b.csv --k 10
```

## 📌 Notes for Judges
- The API implements a **cold-start fallback** when user history is short.
- The system supports **Nigerian stylistic prompts** via `utils.py`.
- The repository is structured for **reproducibility and modular review**.

## 🧾 Deployment
Build and run with Docker:
```bash
docker build -t vex-ai .
docker run -p 8000:8000 vex-ai
```

## 📝 Submission Checklist
- [x] Containerized application
- [x] Task A user modeling API
- [x] Task B recommendation API
- [x] Evaluation script for metrics
- [x] Solution paper draft
- [x] GitHub-ready repository structure

## 📄 Solution Paper
See `solution_paper.md` for the architecture, experiments, and ablation study.

---

*VeX AI: Bridging static profiles and dynamic cultural behavior.*
