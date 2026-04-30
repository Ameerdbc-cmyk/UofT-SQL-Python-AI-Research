# Project 1: AI Adoption, Trust & Institutional Clarity Analysis  
Exploratory Data Analysis | Python · SQL · pandas · matplotlib · seaborn  

---

## Overview

This project demonstrates my ability to transform raw survey data into actionable insights by analyzing AI adoption, trust, and institutional clarity among university students.

The dataset was collected as part of independent undergraduate research at the University of Toronto Mississauga (UTM), examining how students across disciplines use AI tools, how much they trust them, and how clearly institutions communicate AI-related expectations.

n = 86 respondents | 5 academic programs | 13 variables  

The quantitative analysis presented here formed the foundation of a mixed-methods research paper (currently under review), integrating both statistical analysis and qualitative insights.

---

## Business Framing

While the dataset is academic, the analytical framework mirrors real-world business problems:

- Understanding **technology adoption across user segments**
- Identifying how **training and communication impact user behavior**
- Analyzing how **confidence drives trust in tools/products**
- Detecting **gaps between policy and user perception**

These insights are directly applicable to:
- Product adoption & user onboarding
- Internal tool rollout (e.g., AI adoption in organizations)
- Change management & training effectiveness
- Customer trust and engagement analysis

---

## Repository Structure


project1-ai-survey-eda/
│
├── AI_Survey_Clean_Data.xlsx # Clean dataset (4 sheets: Raw, Summary, Distributions, Data Dictionary)
├── Project1_AI_Survey_EDA.ipynb # Full EDA + SQL analysis notebook
├── README.md # Project documentation


---

## Key Questions Explored

- How frequently do students across disciplines use AI tools?
- How does **confidence influence trust** in AI outputs?
- How clearly has the institution communicated AI usage policies?
- Do adoption and attitudes differ by academic program?
- Does frequent AI use correlate with positive or negative learning outcomes?

---

## Analytical Approach

### Tools Used
- Python (pandas, matplotlib, seaborn)
- SQL (segmentation, aggregation, cross-tabulation)
- Jupyter Notebook

### Methods
- Data cleaning and label standardization  
- Exploratory data analysis (EDA)  
- Cross-tabulation and segmentation  
- Correlation analysis  
- SQL-based aggregation and filtering  

---

## Key Findings & Business Insights

### 1. Widespread AI Adoption
88% of respondents use AI tools at least occasionally, with ChatGPT as the dominant tool.

**Insight:**  
Adoption is already high — the challenge is not uptake, but **effective governance and guidance**.

---

### 2. Confidence Drives Trust
Moderate positive correlation (r ≈ 0.35) between confidence and trust.

**Insight:**  
Trust in AI is largely driven by user familiarity, suggesting that **training and exposure increase acceptance**.

---

### 3. Institutional Communication Gap (Primary Finding)
Over 60% of students report unclear guidelines, with more than half receiving no instructor guidance.

**Insight:**  
Ambiguity is structurally produced. Lack of communication leads to uncertainty and inconsistent behavior.

**Business Translation:**  
Organizations that fail to define tool usage policies create **risk-averse or misaligned user behavior**.

---

### 4. High-Frequency Users Report Positive Outcomes
Daily users overwhelmingly report positive learning impacts.

**Insight:**  
Concerns about AI harming performance may reflect **non-user assumptions rather than actual user experience**.

---

### 5. Adoption Varies by Program
CS/Math and Commerce students show the highest adoption, confidence, and preparedness, while Humanities students show the lowest.

**Insight:**  
Adoption is shaped by **perceived legitimacy within a domain**, not just utility.

---

### 6. Access is Not a Limiting Factor
Living situation shows no meaningful relationship with AI usage patterns.

**Insight:**  
Adoption is driven by **attitudes and institutional context**, not access.

---

## Example SQL Analysis

```sql
-- AI usage segmentation by program
SELECT Program, `AI Frequency`, COUNT(*) as Count
FROM survey_data
GROUP BY Program, `AI Frequency`
ORDER BY Program, Count DESC;

-- Confidence vs Trust relationship
SELECT Confidence, Trust, COUNT(*) as Count
FROM survey_data
GROUP BY Confidence, Trust
ORDER BY Confidence, Count DESC;

-- Instructor guidance vs clarity
SELECT `Instructor Guidance`, `Guideline Clarity`, COUNT(*) as Count
FROM survey_data
GROUP BY `Instructor Guidance`, `Guideline Clarity`
ORDER BY `Instructor Guidance`, Count DESC;
