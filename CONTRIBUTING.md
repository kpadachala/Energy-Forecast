## Contributing Guide

Thank you for your interest in contributing to the **Seq2Seq LSTM for PJM Energy Forecasting** project!

### Ways to Contribute

- **Bug reports** – incorrect results, crashes, unclear error messages
- **Documentation** – clarifying explanations, improving markdown, adding examples
- **Model improvements** – architecture tweaks, better training strategies, new features
- **Refactoring** – extracting reusable code from the notebook into Python modules

---

### Getting Started

1. **Fork** the repository on GitHub.
2. **Clone** your fork locally.
3. Create a new branch for your work:

```bash
git checkout -b feature/my-improvement
```

4. Set up your environment:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

5. Ensure you can run the notebook end‑to‑end without errors.

---

### Coding Guidelines

- Prefer **clear, readable code** over clever one‑liners.
- When changing model behavior, **briefly document the rationale** in markdown cells.
- Keep the notebook **reproducible**:
  - Avoid hard‑coding machine‑specific paths.
  - Set random seeds where appropriate.
- If you introduce new Python modules (e.g., under `src/`), follow standard Python style (PEP 8).

---

### Submitting Changes

1. Ensure your branch is up to date with `main`.
2. Run through the notebook and confirm:
   - All cells execute without errors.
   - Plots and metrics appear reasonable.
3. Commit with a **clear message** describing the change:

```bash
git commit -m "Improve Seq2Seq decoder regularization"
```

4. Push your branch and open a **Pull Request**:
   - Describe the motivation for your change.
   - Highlight any breaking changes or new dependencies.
   - Attach before/after metrics or plots if applicable.

---

### Reporting Issues

When opening an issue, please include:

- Environment details (OS, Python version, TensorFlow version)
- Exact error messages or stack traces (if any)
- A short description of the steps to reproduce the problem

This helps maintainers triage and address issues more quickly.

