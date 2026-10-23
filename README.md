# CamosunROV Helper Scripts

These are helper script to help calculate certain values, curve fits, etc.

These are not meant to be implemented into CamosunROV firmware directly.

## Setting up the Python environment

The notebooks use Python 3.14 and a virtual environment called `.venv_helper`. The packages are listed in `requirements.txt`.

Run these from the `CamosunROV_HelperScripts` folder.

**Windows (PowerShell)**

```powershell
py -3.14 -m venv .venv_helper
.\.venv_helper\Scripts\activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

If PowerShell blocks the activate script, run this first (it only affects the current terminal):

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

**Selecting the venv in VS Code**

VS Code doesn't auto-detect a venv named `.venv_helper`. Run **Python: Select Interpreter → Enter interpreter path… → Find…** and choose `.venv_helper\Scripts\python.exe`. In a notebook, pick `.venv_helper` from the kernel picker in the top right.

**Updating requirements**

If you install a new package, add it to `requirements.txt` with its version (`pip show <package>` gives the version).

**Getting the latest changes**

When someone updates `requirements.txt`, pull the changes and reinstall into your existing venv:

```powershell
git pull
.\.venv_helper\Scripts\activate
pip install -r requirements.txt
```

pip only installs or upgrades what's changed. It won't remove packages that were taken out of `requirements.txt`, so if you want an exact match, delete the `.venv_helper` folder and recreate it with the setup steps above.
