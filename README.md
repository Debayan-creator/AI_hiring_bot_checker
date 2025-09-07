# AI Candidate Selector

This project is a **full-stack AI-based tool** to help select the most suitable candidates for a job from a list of LinkedIn/form submissions. The system ranks candidates based on **cosine similarity with the job description** and heuristic boosts.

---

## **Features**
- Parses candidate JSON submissions (`form-submissions.json`).
- Cleans and combines relevant candidate text fields (`resume`, `skills`, `experience`, `cover letters`, `LinkedIn profiles`) into a single string.
- Converts text to **lowercase and removes special characters** for AI matching.
- Uses **Sentence Transformers (`all-MiniLM-L6-v2`)** to compute cosine similarity between candidates and job description.
- Adds **heuristic boosts** (portfolio, years of experience, etc.) to improve ranking.
- Computes a **final score** and selects **top N candidates**.
- Saves top candidates to **CSV** for further review.
- Can visualize candidate similarity using a **heatmap**.

---

## **Project Structure**
ai_candidate_selector/
│
├─ ai_candidate_selector.py # Main Python script
├─ form-submissions.json # Input JSON file with candidate data
├─ top_candidates.csv # Output CSV with top N candidates
├─ requirements.txt # Python dependencies
└─ README.md # Project documentation

yaml
Copy code

---

## **Installation**
1. Clone the repository:
```bash
git clone https://github.com/username/repo_name.git
cd repo_name
Create a virtual environment (optional but recommended):

bash
Copy code
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Make sure your form-submissions.json is in the project folder.

Usage
bash
Copy code
python ai_candidate_selector.py