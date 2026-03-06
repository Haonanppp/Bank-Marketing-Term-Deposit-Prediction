# Bank Marketing Term Deposit Prediction (ANN)

Predict whether a client will subscribe a **term deposit** (`y`) based on **direct marketing phone call** campaign data from a Portuguese banking institution.

This project covers:
- Exploratory analysis of attributes (EDA)
- Deep Learning baseline (ANN)

Dataset source (UCI):
- http://archive.ics.uci.edu/ml/datasets/Bank+Marketing

---

## Dataset Overview

The data comes from **direct marketing campaigns (phone calls)**. Often, more than one contact to the same client is required to assess if the product (bank term deposit) will be subscribed (`yes`) or not (`no`).

### Target
- `y`: has the client subscribed a term deposit? (`yes` / `no`)

### Features (high level)
**Bank client data**
- `age` (numeric)
- `job` (categorical)
- `marital` (categorical)
- `education` (categorical)
- `default` (categorical)
- `housing` (categorical)
- `loan` (categorical)

**Last contact of the current campaign**
- `contact` (categorical: `cellular`, `telephone`)
- `month` (categorical)
- `day_of_week` (categorical)
- `duration` (numeric, seconds)

**Other campaign attributes**
- `campaign` (numeric)
- `pdays` (numeric; 999 means not previously contacted)
- `previous` (numeric)
- `poutcome` (categorical)

**Social & economic context**
- `emp.var.rate` (numeric)
- `cons.price.idx` (numeric)
- `cons.conf.idx` (numeric)
- `euribor3m` (numeric)
- `nr.employed` (numeric)

### ⚠ Important note about `duration`
`duration` strongly affects the target and is **not known before the call is performed**.  
- If your goal is a **realistic predictive model before calling**, you should **exclude `duration`**.
- You can keep it for **benchmarking** to see the upper bound when post-call information is available.

This repo supports both:
- **Realistic setting:** drop `duration`
- **Benchmark setting:** keep `duration`
