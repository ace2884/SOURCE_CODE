# PAD - Principled Adversarial Malware Detection (UI)

This project is a small Tkinter GUI that trains and evaluates SVM and simple neural networks on a CSV dataset. The GUI expects the dataset CSV to be in the `dataset/` folder and the label column to be the last column.

## Quick plan
- Create a clean Python environment (recommended: `.venv` or `conda` env).
- Install dependencies (see `requirements.txt` or the stricter `install_requirements.txt`).
- Run `Main.py`.

## Recommended (venv) — simplest
1. Create and activate a venv in the project folder (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate
```

2. Upgrade pip and install the main requirements:

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

3. Run the GUI:

```powershell
python Main.py
```

4. If VS Code shows unresolved imports, select the interpreter: Command Palette → `Python: Select Interpreter` → choose `.\.venv\Scripts\python.exe` and reload the window.

## If you must reproduce the exact old package set (may require conda)
- The file `install_requirements.txt` contains many pinned, older packages (including `tensorflow==1.14.0`) that usually require Python 3.6–3.7 and conda-installed binaries.
- Use conda if you need that exact stack:

```powershell
conda create -n pad-env python=3.7 -y
conda activate pad-env
conda install -c conda-forge numpy pandas matplotlib scikit-learn h5py -y
pip install -r install_requirements.txt
```

Notes: `install_requirements.txt` may contain entries that fail to install on modern Python (for example `tensorflow==1.14.0`, `Keras==2.3.1` and a placeholder `package-name==0.1`). Remove or update those lines if pip errors out.

## Troubleshooting
- If `tensorflow` fails on Windows, try `pip install tensorflow-cpu` or use conda with prebuilt binaries.
- `mysqlclient` may require Visual Studio Build Tools or use `conda install -c conda-forge mysqlclient`.
- If a package is unknown (e.g. `package-name==0.1`), remove it from the file before installing.

## Verify installs
After installing, run:

```powershell
python -c "import sys, importlib; modules=['numpy','pandas','matplotlib','sklearn','keras','genetic_selection']; print('PYTHON', sys.executable);
for m in modules: 
	try: importlib.import_module(m); print(m+': OK')
	except Exception as e: print(m+': ERROR ->', e)
```

## Run the app
Start the GUI after installation:

```powershell
python Main.py
```

If you paste any pip install errors here I will help fix them (suggest alternate versions or conda installs).
