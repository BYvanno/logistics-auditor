# The "Last Mile" Logistics Auditor
**Client:** Veridi Logistics (Global E-Commerce Aggregator)

---

## A. Executive Summary

Analysis of 99,441 orders from the Olist Brazilian E-Commerce dataset reveals that approximately 6.8% of delivered orders were late or super late. The problem is strongly regional — northeastern states (AL, MA, SE) suffer late delivery rates of 15–21%, compared to southern states (SP, MG, PR) which perform best due to proximity to distribution centers. Late deliveries directly correlate with poor customer reviews, with on-time orders averaging 4.29/5 stars versus 1.74/5 for super-late orders. Peak delay periods occur in Q1 (January–March), suggesting post-holiday logistics strain that requires proactive capacity planning.

---

## B. Project Links

| Deliverable | Link |
|-------------|------|
| 📓 Notebook | *(Add your Google Colab or GitHub notebook link here)* |
| 📊 Dashboard | [Veridi Logistics - Delivery Performance Dashboard](https://datastudio.google.com/reporting/6dee546d-2006-4d89-8e55-774dfb265c82) |
| 📑 Presentation | *(Add your PowerPoint/PDF link here)* |

> ⚠️ All links are set to "Anyone with the link can view"

---

## C. Technical Explanation

### Data Cleaning
- Loaded 5 CSV files from the Olist dataset using pandas
- Deduplicated reviews by keeping the most recent review per `order_id` (some orders had multiple reviews), preventing row inflation from 99,441 to 99,992
- Converted date columns to datetime format for accurate delay calculations
- Excluded canceled/unavailable orders (flagged as "Undelivered") from delivery performance analysis
- Used relative file paths throughout for reproducibility

### Delay Classification
Orders were classified into three categories:
- **On Time**: `days_difference <= 0`
- **Late**: `0 < days_difference <= 5`
- **Super Late**: `days_difference > 5`

### Candidate's Choice: Peak Late Delivery Periods Over Time
I added a time-series analysis of late delivery rates by month to identify *when* during the year delays are worst. This feature has direct business value because it enables Veridi Logistics to anticipate high-risk periods and proactively scale capacity before demand surges. The analysis revealed that **March 2018 had the highest late rate at 18.93%**, with Q1 (January–March) consistently showing elevated delay rates — likely driven by post-holiday order surges and reduced carrier capacity.

---

## Pre-Submission Checklist

- [x] GitHub Repo is Public
- [x] `.ipynb` notebook uploaded
- [x] HTML export uploaded
- [x] Raw CSV files NOT uploaded (`.gitignore` applied)
- [x] Relative paths used in code
- [x] Dashboard link is publicly accessible
- [x] User Stories 1–4 completed
- [x] Bonus story (Portuguese → English translation) completed
- [x] Candidate's Choice challenge completed and explained
