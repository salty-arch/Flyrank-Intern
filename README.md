# FlyRank ML Internship: CTR Opportunity Scoring

> **Which client pages should get title rewrites first?** An ML pipeline that answers this using real search-performance data.
>
> 📄 **[Read the research paper](https://salty-arch.github.io/Flyrank-Intern/)**

## What I built
My 8-week capstone for the FlyRank Machine Learning Track (Applied Search Intelligence), Lane 4: **CTR / Engagement Opportunity Scoring.** It ranks pages by how far their click-through rate lags behind what their ranking tier would predict, weighted by impression volume, so rewrite effort goes where it should pay off most.

## Technologies
Python, Jupyter / Google Colab, pandas, scikit-learn (Logistic Regression, Random Forest), DuckDB, Parquet, Hugging Face Datasets, GitHub Pages (for the paper)

## My role
Sole author of the capstone: problem framing, data exploration, feature building, the hand-written baseline, model training and evaluation, the research paper, the action playbook, and the project write-up.

## Approach
1. **Frame the problem** as a prioritization task: which pages are worth fixing first?
2. **Baseline:** a transparent, hand-written scoring formula based on CTR-vs-tier mismatch and impression volume
3. **Models:** Logistic Regression and Random Forest trained on FlyRank's warehouse data, queried with DuckDB over Parquet (via Hugging Face)
4. **Evaluate** with Precision@20: of the 20 pages each method ranks highest, how many truly deserve a rewrite?

## Results
| Method | Precision@20 |
|---|---|
| Hand-written baseline | 0.15 |
| Logistic Regression | **0.50** |
| Random Forest | **0.50** |

Both learned models lifted precision about 3x over the hand-written rule.

## Deliverables
- 📄 Deployed [research paper](https://salty-arch.github.io/Flyrank-Intern/)
- 🧭 Tier-aware action playbook with rewrite recommendations
- 📓 Notebooks and scripts: [`notebooks/`](notebooks), [`scripts/`](scripts), and my capstone work in [`work/`](work)

## Data and ethics
This repo follows FlyRank's data-use terms (`DATA_USE.md`): only anonymized data, no client names, URLs, or keywords, and no raw datasets committed. Results are framed as **observed and directional decision-support**, not claims about Google's algorithm.

## Run it
```bash
git clone https://github.com/salty-arch/Flyrank-Intern
cd Flyrank-Intern
pip install -r requirements.txt
python scripts/run_all.py            # reference pipeline on the bundled anonymized sample
```
Or open the notebooks in Colab. Setup details are in [SETUP.md](SETUP.md); every file is explained in [GUIDE.md](GUIDE.md).

## Acknowledgements
Built on the FlyRank ML Internship starter template (MIT licensed). Track leads: Mirza Ašćerić (ML) and Hole (data engineering).
