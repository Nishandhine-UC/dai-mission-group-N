## Project Title
The Subjective Poverty Trap: Does Feeling Poor Erode Support for Redistribution?

### Research Question
Does subjectively feeling financially deprived — independent of objective income level and psychological value profile — causally reduce a European citizen's support for government-led income redistribution?

### Why it Matters
This research investigates a crucial aspect of welfare states: how subjective financial stress impacts support for redistribution. If feeling poor leads to individualistic cognition, it could undermine solidarity among those who stand to gain most from redistribution, creating a political 'poverty trap'. Understanding this mechanism has direct implications for welfare state design and addressing inequality in Europe.

### Data
**Source:** European Social Survey (ESS), Round 11 — 2023.

**Unit of Observation:** Individual survey respondents (~50,000 adults from 30 European countries).

**Key Variables:**
*   **gincdif (Target Y):** Government should reduce income differences (Ordinal 1-5)
*   **Y_support_redist (Binary Target):** 1 = supports redistribution
*   **T_subj_poor (Treatment T):** Subjective financial deprivation (0 = comfortable/coping, 1 = difficult/very difficult)
*   **hinctnta (Confounder):** Objective household income decile (Ordinal 1-10)
*   **health (Confounder):** Self-reported health (Ordinal 1-5)
*   **ipcrtiv...impfun (Unsupervised Input):** 21 Schwartz value items
*   **agea, eduyrs, female, cntry, pspwght:** Other confounders and controls.

**Data Quality Issues:** Significant missingness in `hinctnta` (54.6%), survey fatigue, class imbalances in target/treatment variables, and potential measurement/reporting biases due to self-reported data.

### Planned Methods
1.  **Causal Inference (DoWhy - Backdoor Adjustment):** To estimate the causal effect of subjective poverty on redistribution preferences, controlling for confounding factors like income, value archetypes, health, education, age, and gender. Refutation tests will be used to validate findings.
2.  **Supervised Learning (Random Forest vs. Logistic Regression):** To predict redistribution support and identify the most important features. Logistic Regression serves as an interpretable baseline, while Random Forest handles complex interactions and class imbalance. AUC-ROC with stratified 5-fold cross-validation will evaluate model performance.
3.  **Unsupervised Learning (K-Means Clustering):** To reduce the dimensionality of 21 Schwartz value items into a few meaningful 'archetypes'. This addresses multicollinearity and provides a clean categorical confounder for the causal model. k=4 archetypes are chosen based on Schwartz's theory.

### Key Findings (from Discussion & Conclusion)
*   **Subjective Poverty *Increases* Support for Redistribution:** Contrary to the initial hypothesis, feeling financially deprived *substantially increases* support for redistribution (ATE = -0.1804). This effect is robust and statistically unambiguous, even after controlling for various confounders.
*   **Value Archetypes Matter:** Four distinct value archetypes were identified. The 'Vulnerable Solidarians' and 'Resilient Progressives' showed the strongest pro-redistribution sentiment, while 'The Anxious Mainstream' showed the weakest, despite high poverty rates.
*   **Health Amplifies the Effect:** Poor health modestly amplifies the pro-redistribution effect, suggesting compounded precarity intensifies preferences for collective insurance.
*   **Predictive Power:** Random Forest achieved an AUC of 0.6525, outperforming Logistic Regression. Subjective poverty ranked as a meaningful predictor, supporting its independent signal for redistribution preferences.

### Conclusion
In 2023 Europe, feeling financially deprived makes citizens *more* supportive of income redistribution, not less. The 'subjective poverty trap' (where feeling poor reduces support for redistribution) does not operate in this direction. Instead, subjective financial vulnerability activates class-based solidarity. Policy implications suggest that governments should not fear a decline in support for welfare programs due to rising economic anxiety, though different communication strategies may be needed for the 'Anxious Mainstream' subgroup.
