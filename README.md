Trajectory Classes of Post-Stroke Depression Severity and Their Baseline
Predictors: A Multi-Cohort Replication Study

Authors: Lena Oestreich 
Journal: (under review)

Description:
  Latent Class Growth Analysis (LCGA) of post-stroke depression severity
  across three independent cohorts, followed by BCH-corrected regression
  to identify baseline predictors of trajectory class membership.

Cohorts:
  PSS     — Bulgarian Post-Stroke Study         (n=85;  GDS-15)
  EpiUSA  — Epidemiologic Study of Risk of      (n=473; HAMD-17)
            Dementia After Stroke
  SSS     — Sydney Stroke Study                 (n=192; GDS-15 and HAMD-17)

Analyses:
  1.  PSS     — GDS    (within-cohort)
  2.  EpiUSA  — HAMD   (within-cohort)
  3.  SSS     — GDS    (within-cohort)
  4.  SSS     — HAMD   (within-cohort)
  5.  Pooled  — HAMD   (EpiUSA + SSS; primary pooled analysis)
  6.  Pooled  — GDS    (PSS + SSS; secondary pooled analysis)

Model selection strategy (per analysis):
  Step 1: Compare functional forms (linear, quadratic, natural cubic spline)
          using 1-class LGC models; select by lowest BIC.
  Step 2: LCGA class enumeration (2–4 classes) using winning functional form;
          select by BIC, entropy (>0.80), and class size (no class < 5%).

All models estimated via full information maximum likelihood (FIML) in lcmm.
Pooled analyses use within-cohort T-score standardisation (mean=50, SD=10).

BCH regression:
  Primary:   Pooled HAMD (EpiUSA + SSS; n=665)
  Secondary: Pooled GDS  (PSS + SSS;    n=277)
  Predictors: age, sex (female), hypertension, diabetes, global cognition (z)
  Covariate:  cohort (EpiUSA vs SSS / PSS vs SSS)
  Reference:  Class 1 (No Depression)

Dependencies:
  lcmm, dplyr, tidyr, ggplot2, splines, tableone, nnet, broom

Input files (place in data/ subdirectory):
  dataset_PSS_GDS.csv
  dataset_EpiUSA_HAMD.csv
  dataset_SSS.csv
  dataset_pooled_HAMD.csv   (long format; includes time_yrs, HAMD, HAMD_T)
  dataset_pooled_GDS.csv    (long format; includes time_yrs, GDS_T)
  master_PSD_dataset.csv    (merged baseline variables, all cohorts)

Output files (written to output/ subdirectory):
  table1_baseline.csv
  class_assignments_<cohort>.csv  (one per analysis)
  bch_results_pooled_HAMD.csv
  bch_results_pooled_GDS.csv
  plot_assessment_counts.png
  plot_PSS_GDS.png
  plot_EpiUSA_HAMD.png
  plot_SSS_GDS.png
  plot_SSS_HAMD.png
  plot_Pooled_HAMD.png
  plot_Pooled_GDS.png
  plot_forest_HAMD.png
  plot_forest_GDS.png
