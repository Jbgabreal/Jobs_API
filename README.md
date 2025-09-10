## Job Postings API Analysis (NPower Course 9 Peer Group Assignment)

A concise, reproducible walkthrough for collecting and exploring job postings data using APIs and notebooks.

### Objectives
- **Collect** job postings from a public API
- **Store** results in portable formats (JSON, Excel)
- **Explore** and visualize trends with notebooks

### Repository Contents
- `Collecting_Jobs_data_Using_API-Questions.ipynb` — Q&A-style notebook exploring API access patterns and results
- `Jobs_API.ipynb` — main data collection and analysis workflow
- `jobs.json` — sample/exported raw job data (JSON)
- `job-postings.xlsx`, `github-job-postings.xlsx` — tabular exports for analysis or sharing
- `anaconda_projects/db/project_filebrowser.db` — local notebook/browser state (can be ignored)

### Quickstart
1) Clone the repository
```bash
git clone <your-repo-url>.git
cd "Course 9 peer group assignment"
```

2) Create a Python environment (Anaconda recommended)
```bash
conda create -n jobs-api python=3.10 -y
conda activate jobs-api
```

3) Install common dependencies
```bash
pip install jupyter notebook pandas requests matplotlib seaborn
```

4) Launch notebooks
```bash
jupyter notebook
```
Open `Jobs_API.ipynb` to run the end-to-end flow. Use `Collecting_Jobs_data_Using_API-Questions.ipynb` for deeper API exploration.

### Notes on Data & Reproducibility
- The `jobs.json` and Excel files are example outputs. Regenerating them may produce different results over time as APIs update.
- If the API requires an access token in the future, avoid hardcoding secrets in notebooks. Prefer environment variables (e.g., `os.getenv("API_KEY")`) and add any `.env` or secret managers to `.gitignore`.
- Large datasets should be committed via Git LFS or excluded with `.gitignore` to keep the repo lightweight.

### Typical Workflow
- Adjust query parameters in the notebook (date ranges, keywords, locations)
- Run the notebook cells to fetch and clean data
- Save outputs to JSON/Excel for downstream use
- Visualize basic trends (counts by role, location, company, tags)

### Suggested .gitignore
If not already present, consider adding a `.gitignore` with entries like:
```gitignore
# Python/Notebook
.ipynb_checkpoints/
__pycache__/
*.pyc
.venv/
.env

# Data (optional)
*.db
*.sqlite
*.sqlite3
*.csv
*.parquet
*.feather
*.tsv

# OS/Editor
.DS_Store
Thumbs.db
```

### Troubleshooting
- If plots don’t render, ensure you’re running all cells in order and the kernel matches the `jobs-api` environment.
- If API requests fail, check network connectivity and any rate limits. Add backoff/retry if needed.

### License
Specify a license (e.g., MIT) if you plan to share publicly.

### Acknowledgements
Thanks to the NPower team and peers for the assignment structure and feedback.
