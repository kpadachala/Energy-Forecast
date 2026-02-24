## Seq2Seq LSTM for PJM Energy Forecasting

This repository contains a **production-style Seq2Seq LSTM forecaster** for PJM energy demand, implemented in the notebook `seq2seq_energy_forecasting.ipynb`.

The model predicts a **24‑hour horizon** of energy consumption from the previous **168 hours** using a multivariate encoder–decoder architecture built on top of TensorFlow/Keras.

### Project Highlights

- **Architecture**: Bidirectional LSTM encoder + LSTM decoder (Seq2Seq)
- **Target**: PJM regional energy demand (`PJME_MW`)
- **Horizon**: 24‑hour ahead forecast from a 168‑hour lookback window
- **Features**:
  - Cyclical time features (hour, month)
  - U.S. holiday indicators
  - Lagged demand features
  - Scaled inputs/outputs with `MinMaxScaler`
- **Metrics**: MAE, RMSE, and detailed horizon analysis

---

### Repository Structure

- `seq2seq_energy_forecasting.ipynb` – main notebook with the full pipeline
- `README.md` – project overview and usage instructions
- `requirements.txt` – Python dependencies for reproducing results
- `.gitignore` – ignore rules for Python and notebook artifacts
- `LICENSE` – open‑source license (MIT by default; customize as needed)
- `CONTRIBUTING.md` – guidelines for contributing
- `CODE_OF_CONDUCT.md` – community standards
- `data/` – (optional) data directory for datasets
  - `data/README.md` – notes on data sources and layout
- `.github/workflows/ci.yml` – minimal CI to verify dependency installation

---

### Data

This project expects the **PJM hourly energy consumption dataset**, commonly distributed as `PJME_hourly.csv` (for example, via Kaggle).

- By default, the notebook loads:
  - `PJME_hourly.csv` from the **repository root**:
    - `forecaster.load_and_clean_data('PJME_hourly.csv')`
- Recommended layout for a cleaner project:
  - Place the dataset under `data/` (for example: `data/PJME_hourly.csv`)
  - Update the notebook call accordingly:

```python
df = forecaster.load_and_clean_data('data/PJME_hourly.csv')
```

The dataset is **not committed** to this repository to keep the repo lightweight and avoid licensing issues. Please download it from its original source and place it locally before running the notebook.

---

### Environment Setup

You can use either **pip** or **conda**. The simplest way is via `pip` and `requirements.txt`.

#### 1. Create and activate a virtual environment (recommended)

On Windows (PowerShell):

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

On macOS/Linux (bash/zsh):

```bash
python -m venv .venv
source .venv/bin/activate
```

#### 2. Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

This will install TensorFlow, scikit‑learn, pandas, and other packages used in the notebook. The notebook currently targets **TensorFlow 2.20.0**.

#### 3. (Optional) Install Jupyter

If you do not already have a Jupyter environment:

```bash
pip install jupyterlab
```

---

### Running the Notebook

1. **Ensure the dataset is available**:
   - Place `PJME_hourly.csv` in the repository root (or under `data/` and update the path in the notebook).
2. **Activate your virtual environment** and install dependencies:
   - `pip install -r requirements.txt`
3. **Start Jupyter**:

```bash
jupyter lab
```

4. Open `seq2seq_energy_forecasting.ipynb`, run all cells in order, and verify that:
   - Data loads successfully
   - The Seq2Seq model trains without errors
   - Evaluation cells produce metrics and plots

---

### Contributing

Contributions are welcome! See `CONTRIBUTING.md` for guidelines on:

- Reporting issues and bugs
- Proposing new features or model variations
- Coding style and pull‑request expectations

---

### License

This project is licensed under the **MIT License**. See `LICENSE` for details.

