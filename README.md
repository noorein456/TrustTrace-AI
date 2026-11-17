TrustTrace AI

 A Provenance-Aware Framework for Detecting and Assessing Silent Data Manipulation in Machine Learning Training Pipelines

 1. Project Overview

TrustTrace AI is a machine learning security application designed to identify and assess suspicious data manipulation in training datasets.

The system combines dataset validation, data integrity verification, provenance tracking, anomaly detection and model performance comparison to help users understand how potentially manipulated training data can affect machine learning models.

The application is designed to support human review of suspicious records rather than automatically declaring records malicious.

## 2. Problem Statement

Machine learning models depend on the quality and integrity of their training data. However, training datasets can be silently modified through label flipping, feature manipulation or malicious data injection.

Such changes may go unnoticed and negatively affect model performance and reliability.

TrustTrace AI aims to provide a structured framework for detecting suspicious changes, tracking dataset provenance and assessing their impact on machine learning models.

## 3. Main Objectives

- Upload and validate structured CSV datasets.
- Maintain original datasets and separate processed copies.
- Generate SHA-256 dataset fingerprints.
- Track dataset versions and provenance events.
- Detect suspicious records using Isolation Forest and KNN-based label consistency.
- Simulate selected data manipulation techniques.
- Calculate and explain suspiciousness scores.
- Compare models trained on clean and manipulated datasets.
- Generate visual reports for human review.

## 4. Project Scope

The initial prototype focuses on structured CSV datasets used for supervised classification.

The system investigates:
- Label flipping.
- Feature manipulation.
- Data injection.
- Dataset integrity changes.
- Anomalous records.
- Model performance degradation.

The system does not claim to prove malicious intent or identify attackers. Detection results are indicators that require human review.

## 5. System Architecture

The application consists of four modules connected through one shared FastAPI backend.

1. Member 1 — Dataset Upload and Preprocessing.
2. Member 2 — Database, Integrity and Provenance.
3. Member 3 — AI-based Suspicious Data Detection.
4. Member 4 — Frontend, Model Impact and Integration.

The frontend communicates with the shared backend, which communicates with the MySQL database and the four project modules.

## 6. Technology Stack

**Frontend**
- HTML
- CSS
- JavaScript

**Backend**
- Python 3.11
- FastAPI
- Uvicorn
- Pydantic

**Data Processing and Machine Learning**
- Pandas
- NumPy
- Scikit-learn

**Database and Provenance**
- MySQL
- SQLAlchemy
- PyMySQL
- NetworkX

**Testing**
- Pytest
- HTTPX

**Version Control**
- Git
- GitHub

## 7. Repository Structure

```text
TrustTrace-AI/
├── frontend/
├── backend/
│   └── app/
│       ├── api/
│       ├── core/
│       ├── database/
│       └── modules/
│           ├── member1_dataset/
│           ├── member2_provenance/
│           ├── member3_detection/
│           └── member4_model_impact/
├── tests/
├── docs/
├── storage/
├── sample_data/
├── scripts/
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## 8. Local Installation and Execution

**Prerequisites**
- Python 3.11
- Git
- MySQL Server

**Clone the repository**

```bash
git clone https://github.com/noorein456/TrustTrace-AI.git
cd TrustTrace-AI
```

**Create a virtual environment**

```bash
python -m venv .venv
```

**Activate it on Windows**

```powershell
.venv\Scripts\Activate.ps1
```

**Install dependencies**

```bash
pip install -r requirements.txt
```

Configure the database using the `.env.example` template. Create your local `.env` file with your own credentials.

The final integrated application will be launched using:

```powershell
.\start_project.bat
```

The planned local application address is:

http://localhost:8000

Startup instructions will be finalised after backend and database integration.

## 9. Team Responsibilities

| Member | Responsibility |
|---|---|
| Member 1 | Dataset upload and preprocessing |
| Member 2 | Database, integrity and provenance |
| Member 3 | AI-based suspicious data detection |
| Member 4 | Frontend, model impact and integration |

## 10. Git Collaboration Workflow

- `main` — stable project version.
- `develop` — shared integration branch.
- `member1-dataset` — Member 1.
- `member2-provenance` — Member 2.
- `member3-detection` — Member 3.
- `member4-impact` — Member 4.

Members work on their assigned branches and submit pull requests into `develop`. The integrated and tested version is merged into `main`.

## 11. Research and Evaluation

The project evaluates suspicious-data detection using precision, recall, F1-score and false-positive rate against controlled simulated manipulation.

Model impact is evaluated by comparing clean-trained and manipulated-trained models on the same untouched clean test dataset.

## 12. Project Status

Initial repository structure created. Module implementation, API integration, database configuration and end-to-end testing are in progress.
