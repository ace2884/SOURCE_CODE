
# PAD - Principled Adversarial Malware Detection (UI)

Short: create a Python environment, install dependencies, and run `Main.py`.

Prerequisites
- Python 3.8+ (or use conda for older stacks).
- Git/VS Code (optional).
- Dataset CSV placed in `dataset/` with the label as the last column.

Option 1 — Recommended: venv (Windows PowerShell)
1. Create and activate venv:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate
```

2. Install required packages:

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

3. Verify quick imports (optional):

```powershell
python -c "import importlib,sys; mods=['numpy','pandas','matplotlib','sklearn','keras','genetic_selection']; print('PYTHON',sys.executable); 
for m in mods:
	try: importlib.import_module(m); print(m+': OK')
	except Exception as e: print(m+': ERROR ->', e)
"
```

4. Run the app:

```powershell
python Main.py
```

5. In VS Code: Command Palette → `Python: Select Interpreter` → pick `.\.venv\Scripts\python.exe`, then reload window.

Option 2 — Conda (if you must reproduce old pinned packages)
- Use conda when installing old TensorFlow or binary packages (safer on Windows).

```powershell
# in Anaconda Prompt or PowerShell with conda
conda create -n pad-env python=3.7 -y
conda activate pad-env
conda install -c conda-forge numpy pandas matplotlib scikit-learn h5py -y
pip install -r install_requirements.txt
```

Notes about `install_requirements.txt`
- It contains tightly pinned, older packages (e.g. `tensorflow==1.14.0`) that usually require Python 3.6–3.7 and may fail on modern Python.
- Remove placeholder or invalid lines (for example `package-name==0.1`) before installing.

Troubleshooting
- If `tensorflow` fails on Windows, try `pip install tensorflow-cpu` or prefer conda packages.
- `mysqlclient` often requires build tools; use `conda install -c conda-forge mysqlclient` on Windows.
- If Pylance shows unresolved imports after successful pip install, confirm VS Code uses the same interpreter and reload the window.

If you paste the exact pip/conda error output here I will diagnose the failing package and provide an exact fix.
