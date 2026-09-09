# End-to-End MLOps Pipeline

A modular, production-ready machine learning pipeline implementing end-to-end MLOps workflows: from automated data ingestion and validation to training, experiment tracking, and model registration.

---

## Architecture & Workflow

The pipeline executes sequentially through five core stages:

1. **Data Ingestion:** Downloads and extracts raw dataset artifacts.
2. **Data Validation:** Checks schemas, column types, and data integrity.
3. **Data Transformation:** Handles preprocessing, feature engineering, and train/test splits.
4. **Model Training:** Fits regression/classification estimators based on defined parameters.
5. **Model Evaluation & Tracking:** Evaluates performance metrics (`RMSE`, `MAE`, `R2`), logs artifacts, and registers versions to remote MLflow on DagsHub.


```

Data Ingestion ➔ Data Validation ➔ Data Transformation ➔ Model Trainer ➔ Model Evaluation (MLflow)

```

---

## Project Structure

```text
├── config/
│   └── config.yaml          # Pipeline directory paths and remote artifact definitions
├── params.yaml              # Hyperparameters (e.g., alpha, l1_ratio)
├── schema.yaml              # Dataset schema definition and validation rules
├── src/data_science_projects/
│   ├── components/          # Implementation logic for each pipeline stage
│   ├── config/              # Configuration manager mapping YAML to entities
│   ├── entity/              # Immutable data contracts and configs
│   ├── pipeline/            # Stage orchestration scripts
│   └── utils/               # Common helper utilities (YAML, JSON, directory ops)
├── artifacts/               # Generated run outputs (ignored by Git)
├── main.py                  # Pipeline execution runner
├── requirements.txt         # Production dependencies
└── Dockerfile               # Containerization specifications

```

---

## Getting Started

### 1. Clone & Set Up Environment

```bash
git clone [https://github.com/imehranasgari/data_science_projects.git](https://github.com/imehranasgari/data_science_projects.git)
cd data_science_projects

python -m venv venv
# Windows:
venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt

```

### 2. Configure Environment Variables

Create a `.env` file in the root directory:

```ini
MLFLOW_TRACKING_URI=[https://dagshub.com/imehranasgari/data_science_projects.mlflow](https://dagshub.com/imehranasgari/data_science_projects.mlflow)
MLFLOW_TRACKING_USERNAME=your_username
MLFLOW_TRACKING_PASSWORD=your_dagshub_token

```

### 3. Run Pipeline

Run the full end-to-end pipeline:

```bash
python main.py

```

---

## Tech Stack

* **Language:** Python
* **ML Framework:** Scikit-Learn, Pandas, NumPy
* **Experiment Tracking:** MLflow, DagsHub
* **Pipeline Config:** YAML, Pydantic/DataClasses
* **Containerization:** Docker

```

```
### Workflows--ML Pipeline

1. Data Ingestion
2. Data Validation
3. Data Transformation-- Feature Engineering,Data Preprocessing
4. Model Trainer
5. Model Evaluation- MLFLOW,Dagshub

## Workflows

1. Update config.yaml
2. Update schema.yaml
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py