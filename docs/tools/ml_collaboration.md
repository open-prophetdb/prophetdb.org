---
title: "OpenProphetDB"
---

# Best Practices for ML Collaboration

## Data Lake

![lakeFS](/assets/images/nas.png)

Lakefs Website: [https://lakefs.3steps.cn](https://lakefs.3steps.cn)

VS Code Extension: [https://github.com/yjcyxky/lakefs-vscode-extension](https://github.com/yjcyxky/lakefs-vscode-extension)

lakeFS brings Git-like workflows to data lakes. It allows teams to manage data evolution, run reproducible experiments, and collaborate safely on large datasets. This document outlines recommended practices for using lakeFS effectively in ML and data science workflows.

---

### Core Principles

1. **Data immutability through commits**

   * Every commit in lakeFS represents a complete, immutable snapshot of the repository at that point in time.
   * A commit ID or tag uniquely identifies the dataset version used in an experiment.

2. **Branches for isolation**

   * Branches provide isolated workspaces, ensuring that experiments or data transformations do not interfere with the main (production) data.
   * Just like Git, branches can later be merged selectively.

3. **Remote-first architecture**

   * The lakeFS repository in object storage is the source of truth.
   * Local directories (linked via `lakectl local`) are conveniences for development, but pipelines should reference remote lakeFS URLs directly.

---

### Branching Strategy

#### Main Branch (`main` or `production`)

* **Purpose**: Serve as the single source of truth for clean, validated data.
* **Contents**:

  * Curated datasets ready for downstream consumption.
  * Data changes from ingestion, cleaning, or bug fixes.
  * Stable commits, often tagged (`cleaned-v1`, `training-2025-01`).

#### Experiment Branches

* **Purpose**: Contain artifacts of ML workflows.
* **Contents**:

  * Feature engineering outputs.
  * Train/test splits.
  * Intermediate caches and embeddings.
  * Trained model files.
  * Logs and metrics.
* **Data source**: Always pulled from the main branch (or tagged commits) via lakeFS URLs.
* **Naming conventions**:

  * `exp-transformer-v2`
  * `exp-featureA`
  * `exp-xgboost`

---

### Referencing Data

#### Always Use lakeFS URLs

Instead of relying on local directories, reference data directly with lakeFS URIs in pipelines and experiment trackers:

```yaml
data:
  train: lakefs://bdnf-mecfs@cleaned-v1/train.csv
  test:  lakefs://bdnf-mecfs@cleaned-v1/test.csv
outputs:
  model: models/exp-transformer-v2/model.pkl
  metrics: metrics/exp-transformer-v2.json
```

**Why?**

* Guarantees reproducibility (commit/tag = exact dataset snapshot).
* Consistent across environments (local, cloud, cluster).
* Ensures experiment lineage is preserved.

#### Local Checkout for Development Only

* Use `lakectl local link` and `lakectl local checkout` for exploratory work.
* Example:

  ```bash
  lakectl local link . lakefs://bdnf-mecfs/main
  lakectl local checkout . --ref cleaned-v1
  ```
* Not recommended for pipelines, since local directories vary by environment.

---

### Handling Data Evolution

1. **Commit often**

   * Treat commits as checkpoints in data cleaning or transformation.
   * Example:

     ```bash
     lakectl commit -m "Normalized BDNF values, removed outliers"
     ```

2. **Tag milestones**

   * Mark important dataset versions for experiments or releases.
   * Example:

     ```bash
     lakectl tag create cleaned-v1 --id <commit_id>
     ```

3. **Branch for experiments**

   * Each new experiment should run in its own branch, referencing the appropriate main commit/tag for input data.
   * Outputs (models, metrics) remain isolated in the branch.

4. **Merge cautiously**

   * Only merge back into `main` when the branch produces validated new data (e.g., engineered features).
   * Do not merge transient experiment artifacts (models/logs) into `main`.

---

### Integrating with ML Pipelines

* **Airflow / Kubeflow / Prefect**: Always store input datasets as lakeFS URLs.
* **MLflow / W\&B**: Record both code commit (Git) and data commit/tag (lakeFS) for reproducibility.
* **Training jobs**: Pass data URIs to the training script, e.g.:

  ```bash
  python train.py \
    --train lakefs://bdnf-mecfs@cleaned-v1/train.csv \
    --test lakefs://bdnf-mecfs@cleaned-v1/test.csv
  ```

---

### Summary of Best Practices

* ✅ Keep **main branch** clean and stable — it’s the trusted dataset.
* ✅ Use **experiment branches** to isolate ML workflow outputs.
* ✅ Reference **data with lakeFS URLs** in pipelines, not local directories.
* ✅ Commit and tag often to capture data evolution.
* ✅ Track data lineage by recording lakeFS commit IDs alongside code commits.
* ✅ Merge back only validated data transformations, not transient experiment files.

---

📌 **Key Takeaway**:
**Think of lakeFS like Git for your data**. Main branch holds production-ready data; experiment branches hold model outputs and exploratory work. Always use lakeFS URLs in pipelines to guarantee reproducibility and collaboration.


## Wandb - AI Developer Platform

Use Weights & Biases to train and fine-tune models, and manage models from experimentation to production.