🧪 Glass Dissolution Data Relevance Screening Workflow

This workflow is designed to systematically evaluate the relevance of scientific articles for inclusion in a machine learning database aimed at predicting the initial dissolution rate of glasses.
🔍 Purpose

To build a high-quality dataset, each article must provide essential experimental information that can support accurate and consistent machine learning modeling. This screening workflow ensures only articles with complete, quantitative, and usable data are included.
✅ Relevance Criteria

Each glass or experimental condition in an article is considered relevant only if all three of the following are explicitly provided:

    Complete Chemical Composition

        Given in weight percentages (e.g., SiO₂, B₂O₃, Na₂O, etc.)

        The sum must be close to 100% (±5%)

    Explicit Initial Dissolution Rate

        Provided as a numeric value with units (e.g., g·m⁻²·d⁻¹)

        Measured in initial (pre-saturation) conditions

        Normalized (e.g., by geometric or BET surface area), with method specified

    At Least One Experimental Parameter

        e.g., Initial pH, test temperature, solution volume, surface area, or flow rate

        Must be clearly linked to the dissolution rate measurement

🚫 Exclusion Criteria

Articles (or individual datasets within articles) are excluded if any of the following apply:

    The composition is partial or does not sum to ~100%

    The dissolution rate is missing, only shown in graphs, or lacks units/normalization

    No experimental parameter is associated with the rate measurement

📄 Evaluation Output Format

Each article is reviewed and summarized using the following format:

1. Article relevance: [Yes/No]  
2. Justification: [Brief explanation, e.g., which criteria are met or missing for each glass or condition]

Example:

1. Article relevance: Yes  
2. Justification: "For glass G0.40Nd4C, the article gives a complete composition (total = 99.99%), an explicit initial rate (V₀,Si = 0.8 g·m⁻²·d⁻¹, normalized to Sgeo), and the temperature (100 °C), so it is relevant."

🛠 Usage

Use this workflow as a manual review protocol when extracting data from literature. It ensures consistency, objectivity, and alignment with the data quality requirements for modeling.
