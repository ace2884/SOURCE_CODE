# PAD - Principled Adversarial Malware Detection (UI)

This project is a Tkinter GUI that runs SVM and Neural Network classifiers (optionally with feature selection using a genetic algorithm) on a CSV dataset.

Setup (Windows PowerShell)

1. Create and activate a virtual environment:

```
python -m venv venv
.\\venv\\Scripts\\Activate
```

2. Install dependencies:

```
pip install -r requirements.txt
```

3. Run the app:

```
python Main.py
```

Notes
- Ensure your dataset CSV is in the `dataset/` folder and has the label column as the last column.
- If you encounter missing packages for `tkinter`, install the OS-specific package or use the system Python that includes tkinter.
