# A/B Testing Analysis: Evaluating AI-Driven Decision Support in Loan Approval

This repository contains a project as part of the MSc Business Analytics program at Warwick Business School. The objective was to assess whether a new AI model improves decision quality of loan officers compared to an existing model, using a structured A/B testing framework.

---

## 📂 Repository Contents

- [**`AB_testing_data.csv`**](./AB_testing_data.csv): Cleaned dataset used for statistical testing and evaluation.
- [**`AB_testing_report.pdf`**](./AB_testing_report.pdf): Full analytical report including methodology, statistical outputs, and business interpretation.

---

## 📊 Dataset Overview

The dataset contains experimental data collected over 10 days, representing the performance of loan officers under two conditions:
- **Control**: Using the existing decision model.
- **Treatment**: Using a newly deployed AI-assisted model.

Each row represents a single officer’s activity for one day.

**Key variables include:**
- `typeI_init`, `typeI_fin`: Type I errors (good loans rejected)
- `typeII_init`, `typeII_fin`: Type II errors (bad loans accepted)
- `revised_per_ai`, `revised_agst_ai`: Decisions revised with/against AI input
- `confidence_init_total`, `confidence_fin_total`: Officer confidence scores
- `complt_init`, `complt_fin`, `fully_complt`: Completion metrics

---

## 🧠 Project Objective

To determine whether the newly developed AI model improves the quality of loan decisions, focusing on the trade-off between:
- Reducing **Type II errors** (approving bad loans)
- Minimizing **Type I errors** (rejecting good loans)

---

## 📈 Methodology

1. **Exploratory Data Analysis**
   - Assessed baseline group balance
   - Examined review completion rates and consistency
   - Identified review revisions after AI interaction

2. **Overall Evaluation Criterion (OEC)**
   - Defined as:  
     `OEC = 0.5 × ΔType II errors + 0.5 × ΔType I errors`
   - Captures both types of decision-making risk

3. **A/B Testing**
   - Welch’s t-test used to compare OEC between control and treatment groups
   - **Result**: Statistically significant performance **decline** in the treatment group

4. **Effect Size**
   - Cohen’s d = **-0.87** (large negative effect), indicating the new model worsened decision outcomes

5. **Power Analysis**
   - Minimum of **64 officers per group** required for 80% power at 95% confidence

---

## ✅ Results Summary

- 📉 **Treatment group underperformed** significantly based on OEC
- ❌ Increased inconsistency and volatility in decision outcomes
- 🔍 No meaningful benefit observed from AI recommendations

| Metric                  | Result               |
|-------------------------|----------------------|
| p-value (Welch’s t-test)| 0.022                |
| Effect Size (Cohen’s d) | -0.87 (large)        |
| Minimum N for Power     | 64 per group         |

---

## 💡 Key Insights

- The new AI model **negatively impacted decision quality**
- Officers in the treatment group showed greater **uncertainty** and **volatility** in decision revision
- **Type II errors (bad loans approved)** were not reduced meaningfully

---

## 📌 Recommendations

- **Terminate current experiment** due to statistically and practically negative results
- **Redesign future experiments**:
  - Include individual loan-level tracking
  - Improve officer training on AI model interpretation
  - Reconsider the business weighting of Type I vs. Type II errors
- Ensure **sample size** is large enough for meaningful effect detection

---

## 📎 How to Use This Repository

You can:
- Open the CSV file to review the experimental data structure
- Refer to the PDF report for all visualizations, R code outputs, and statistical tests

---

## 📬 Contact

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/benjamin-sachse-consultant/) or reach out for collaboration or further discussion on A/B testing and AI deployment in decision systems.
