# igebra.ai


# Student Analytics & Dashboard

This repo contains:
- `students.csv` — synthetic dataset
- `analysis_ml.ipynb` — EDA, correlations, ML model, clustering
- `student-dashboard/` — Next.js app (charts, table, insights)

## Quick Start

### 1) Notebook
1. Download: [students.csv](students.csv) and [analysis_ml.ipynb](analysis_ml.ipynb)
2. Open the notebook locally (Jupyter/VS Code) in the same folder as `students.csv`.
3. Run all cells. It will generate:
   - `students_with_personas.csv`
   - `model.pkl`, `scaler.pkl`

### 2) Next.js Dashboard (local)
1. Download & unzip: `student-dashboard.zip`
2. `cd student-dashboard`
3. `npm install`
4. `npm run dev`
5. Open http://localhost:3000

The dashboard includes:
- Overview stats (avg scores, skills, engagement)
- Charts: bar (skill vs avg score), scatter (attention vs score), radar (student profile)
- Searchable/sortable student table (click a row to update radar)
- Insights (calculated correlations client-side)

### 3) Deploy to Vercel
A **Vercel link** is the public URL created after you deploy this Next.js app to Vercel (e.g., `https://student-dashboard-yourname.vercel.app`). Submit that link along with your GitHub repo.

**Steps:**
1. Push this project to GitHub (two folders/files to upload):
   - `student-dashboard/` (the Next.js app)
   - `students.csv` and `analysis_ml.ipynb` (optional: put them in a `/notebooks` folder)
2. Go to https://vercel.com/new and import your GitHub repo.
3. Framework preset: **Next.js**. Leave defaults.
4. Deploy. Vercel will give you a public URL — that URL is your **Vercel link**.

### 4) Suggested Repo Structure
```
.
├─ notebooks/
│  ├─ analysis_ml.ipynb
│  └─ students.csv
├─ student-dashboard/
│  ├─ app/...
│  ├─ components/...
│  ├─ public/students.json
│  ├─ package.json
│  └─ tsconfig.json
└─ README.md
```

### 5) Findings (example — yours may vary slightly)
- Comprehension, focus, and retention show the strongest positive correlations with assessment score.
- Attention correlates positively but typically slightly lower than comprehension/focus.
- Engagement time helps up to ~90 minutes/day; gains diminish beyond that.
- Random Forest generally outperforms Linear Regression on this dataset (check `r²` and `MAE` in the notebook output).
- KMeans (k=3) yields personas such as **Focused Achievers**, **Engaged Strivers**, and **At-Risk (Low Engagement)**.

---

**Tip:** If you want the dashboard to reflect the personas computed in the notebook, export `students_with_personas.csv` as JSON and replace `public/students.json` in the app.
