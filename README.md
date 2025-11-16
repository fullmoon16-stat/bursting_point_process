# bursting_point_process

Code and data for  
**"Discussing Cascading Failures: the Bursting Point Processes Approach"**

This repository contains the R code and data used to produce the results in the manuscript

> *"Discussing Cascading Failures: the Bursting Point Processes Approach"*,  
> submitted to *Applied Stochastic Models in Business and Industry*, Manuscript ID ASMB-25-110.R1.

The focus of this repository is the real cascading failure data analysis in Section 4.2 (WSCC August 1996 blackout) and the associated model–based simulations.

---

## Repository contents

- `wscc1996_analysis.Rmd`  
  R Markdown file containing all code for the WSCC 1996 data analysis and simulations.

- `wscc1996_cascading_events.csv`  
  Data set of the 54 significant events during the August 10, 1996 WSCC blackout, as reported in the NERC report and summarised in Table 1 of the manuscript.

---

## Data description

The file `wscc1996_cascading_events.csv` contains the following variables:

- `sequence` : event index (1–54); corresponds to the event number in Table 1  
- `timeline` : original event time as given in the NERC report (local time on 10 August 1996)  
- `second`   : elapsed time in seconds from the first event  
- `Tn`       : inter-arrival time in seconds between consecutive events  
  (`Tn = second_n − second_{n-1}` with `T1 = 0`)

In the analysis, the truncated data set used for model fitting and for Figure 4 is obtained by selecting the first 38 events (i.e. removing the last 16 failures belonging to the cascade phase-out stage). This truncation is performed inside `wscc1996_analysis.Rmd` and no separate file is required.

---

## What the code reproduces

Running `wscc1996_analysis.Rmd` reproduces the following results in the manuscript:

- **Figure 3** – Cumulative number of failures for the original WSCC data (all 54 events)  
- **Figure 4** – Cumulative number of failures for the truncated data (first 38 events, up to the explosion time)  
- **Table 2** – MLEs, maximised log-likelihoods, AIC and BIC values for the fitted models  
- **Figure 5** – Average of 100 simulated sample paths of the cumulative number of failures \(N(t)\) for each fitted model, compared with the real data  
- **Tables 3–4** – Summary statistics of the explosion time \(T\) from 1000 Monte Carlo simulations under the geometric process and EGPP models  
- **Table 5** – Summary statistics of the explosion time \(T\) for all fitted models (including the Hawkes process)  
- **Figure 6** – Estimated pdfs of the explosion time \(T\) under the fitted models

---

## Contact

If you have questions about the code or data, please contact the corresponding author of the manuscript.
