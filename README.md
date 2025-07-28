
<img width="1634" height="731" alt="image" src="https://github.com/user-attachments/assets/ffbeea7a-2236-4a99-b569-5f5526566165" />

````markdown
# 🧪 Glass Dissolution Data Relevance Screening Workflow

This repository contains a standardized workflow for evaluating the **relevance of scientific articles** for inclusion in a database aimed at **predicting the initial dissolution rate of glasses using machine learning**.


---
## 📌 Purpose

To build a reliable and high-quality dataset, it is crucial to include only studies that provide **complete, quantitative, and standardized data**. This workflow ensures that only relevant data points are selected for machine learning applications by applying strict inclusion criteria.

---

## ✅ Relevance Criteria

Each glass or experimental condition reported in an article is considered **relevant** only if it meets **all three** of the following conditions:

### 1. Complete Chemical Composition
- Provided in weight percentages (e.g., SiO₂, B₂O₃, Na₂O, etc.)
- The total composition must sum to approximately 100% (±5%)
- Partial or incomplete compositions are not accepted

### 2. Explicit Initial Dissolution Rate
- Must be provided as a numeric value with a clear unit (e.g., `g·m⁻²·d⁻¹`, `mg·m⁻²·h⁻¹`, etc.)
- Measured under **initial conditions** (before saturation or the formation of alteration layers)
- Must be **normalized** (e.g., by geometric or BET surface area), and the normalization method must be stated
- Indirect values (e.g., from plots or calculated from slopes) are not accepted

### 3. At Least One Associated Experimental Parameter
At least one of the following must be reported and clearly linked to the measured rate:
- Initial pH
- Test temperature
- Solution volume
- Specific surface area (BET or geometric, if powder)
- Solution flow rate (for dynamic tests)

---

## 🚫 Exclusion Criteria

A data point is considered **not relevant** if **any** of the following conditions apply:
- Composition is incomplete or does not sum to ~100%
- Dissolution rate is missing, only shown in figures, lacks units, or normalization is not specified
- No experimental parameter is reported in connection to the dissolution rate

---

## 🧾 Evaluation Output Format

Each article is manually reviewed and the following summary format is used:

```txt
1. Article relevance: [Yes/No]  
2. Justification: [Brief explanation referencing the three criteria]
````

### ✅ Example (Relevant):

```txt
1. Article relevance: Yes  
2. Justification: "For glass G0.40Nd4C, the article provides a full composition (total = 99.99%), an explicit initial rate (V₀,Si = 0.8 g·m⁻²·d⁻¹, normalized to Sgeo), and the temperature (100 °C), so it is relevant."
```

### ❌ Example (Not Relevant):

```txt
1. Article relevance: No  
2. Justification: "The composition is provided (total = 99.99%) and pH is given (pH = 6), but the initial rate is not explicit—only curves are shown—so the dataset is not relevant."
```

---

## 🛠 How to Use

1. **Read** the full experimental section of each article.
2. **Extract** and record:

   * Composition (%)
   * Explicit initial rate (with units and normalization)
   * At least one linked experimental parameter
3. **Apply** the criteria strictly—do not infer missing data.
4. **Summarize** using the evaluation format above.

This workflow is intended to **ensure data integrity and consistency** when compiling datasets for machine learning models.

---

