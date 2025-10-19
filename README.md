# 🏦 Task 4: Bucket FICO scores

# J.P. Morgan Quantitative Research Virtual Experience

### 📘 Overview
This project builds an **advanced credit risk quantization model** that categorizes continuous **FICO scores** into discrete risk buckets.  
The goal is to estimate the **Probability of Default (PD)** for each bucket and compare different quantization strategies.

---

## 🎯 Objective
To design a **robust and generalizable bucketing algorithm** that:
1. Segments borrowers by credit quality (FICO score).
2. Computes the Probability of Default (PD) for each bucket.
3. Compares **Equal-width**, **Quantile**, and **Log-Likelihood optimized** methods.

---

## ⚙️ Methods Implemented

| Method | Description |
|---------|--------------|
| **Equal-width Binning** | Divides FICO scores into equal ranges (e.g., 300–385, 385–470, ...). |
| **Quantile Binning** | Splits borrowers into buckets containing equal numbers of records. |
| **Log-Likelihood Optimization** | Uses dynamic programming to find bucket boundaries that maximize statistical separation between defaults and non-defaults. |

---

## 🧮 Formula Used

**Log-Likelihood Function**

\[
L = \sum_i [k_i \ln(p_i) + (n_i - k_i)\ln(1 - p_i)]
\]

Where:  
- \(k_i\) = number of defaults in bucket *i*  
- \(n_i\) = total borrowers in bucket *i*  
- \(p_i = k_i / n_i\) = observed PD in bucket *i*  

---

## 📈 Visualization
A comparison chart shows how PD changes across FICO score buckets for different methods:

   ↑
PD(%) | Optimized
| /
| / \ Quantile
| / \ /
|/_/________→ FICO Buckets


The **optimized bucketing** produces smoother transitions and sharper separation between high and low credit risks.

---

## 📊 Example Output
| Method | Avg PD (%) | Buckets | Optimized Boundaries |
|---------|-------------|----------|----------------------|
| Equal-width | 10.42 | 10 | — |
| Quantile | 10.37 | 10 | — |
| Log-Likelihood Optimized | **9.82** | 9 | [300, 420, 520, 610, 680, 740, 780, 810, 835, 850] |

---

## 🧾 Dependencies
```bash
pip install pandas numpy seaborn matplotlib


