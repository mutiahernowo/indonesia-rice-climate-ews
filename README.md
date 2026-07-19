# indonesia-rice-climate-ews
A machine learning-based Early Warning System (EWS) that predicts provincial rice productivity in Indonesia from climate data, flagging at-risk provinces 2–3 months upon the harvest time to support proactive agricultural policy in facing climate change.

## Overview

Climate variability is a major driver of rice productivity volatility across Indonesia, but risk often isn't visible until yield data comes in — by which point it's too late to intervene. This project builds an EWS using climate variables (i.e., rainfall rate, temperature, sunshine time span, humidity, and hot days) to forecast provincial rice productivity ahead of harvest, then classifies provinces into risk tiers based on how current year conditions compare to historical baselines.

## What I did

- Built and compared three models, including **OLS Regression, Random Forest, and XGBoost**, to predict provincial rice productivity from climate variables
- Used **Leave-One-Year-Out cross-validation** to properly evaluate temporal generalisation (critical when predicting across years, not just random
  train/test splits)
- Built **progressive feature sets** (F0 basic -> F1 extended -> F2 full combination) to measure how much predictive value additional climate variables actually add
- Classified provinces into a **risk tier system** (HIGH/MODERATE/NORMAL risk) by comparing current-year monitoring data against 2019–2023 historical baselines
- Produced a CSV alert report as the practical output

## Data sources

- **Climate data**: BMKG (Indonesia's Meteorology, Climatology, and Geophysics Agency), 2014–2019
- **Rice productivity data**: BPS (Statistics Indonesia), for province level, 2014–2019

> Raw data not redistributed in this repo due to size/licensing; see the
> `data/README.md` for source links and how to reproduce the pull.

## Tools

R · XGBoost · randomForest · leave-one-year-out cross-validation ·
tidyverse for data wrangling

## Repository contents

- `scripts/` — data preparation, feature engineering, and modelling scripts
- `report/` — final written report (Business & Data Case Study format)
- `outputs/` — example risk-tier CSV alert report

## Key result

XGBoost with the full (F2) feature set delivered the strongest predictive
performance under leave-one-year-out validation, forming the basis for the
final risk classification system.

## Academic context

Individual assignment, Foundations of Data Science unit, Monash University, 2025.
