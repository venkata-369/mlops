### Step 1: Open Terminal in VS Code

Press **Ctrl + `** (backtick) or go to **Terminal → New Terminal**.

Navigate to your project:

```cmd
cd /d E:\ai-training\Enterprise-Mlops\python-lab
```

Verify:

```cmd
pwd
```

or

```cmd
cd
```

You should be in:

```
E:\ai-training\Enterprise-Mlops\python-lab
```

---

### Step 2: Create a Virtual Environment

```cmd
python -m venv .venv
```

or

```cmd
py -m venv .venv
```

This creates:

```
python-lab
│
├── .venv
├── Untitled-1.ipynb
```

---

### Step 3: Activate the Environment

On Windows:

```cmd
.venv\Scripts\activate
```

You should see:

```
(.venv) E:\ai-training\Enterprise-Mlops\python-lab>
```

---

### Step 4: Install Required Packages

```cmd
python -m pip install --upgrade pip
```

Then:

```cmd
pip install notebook jupyter ipykernel pandas numpy matplotlib
```

---

### Step 5: Register the Kernel

```cmd
python -m ipykernel install --user --name python-lab --display-name "Python Lab"
```

---

### Step 6: Restart VS Code

Close VS Code and open it again.

Open:

```
E:\ai-training\Enterprise-Mlops\python-lab
```

---

### Step 7: Select the Kernel

Open your notebook.

Click **Select Kernel** (top-right).

Choose:

```
Python Lab
```

or

```
Python 3.x (.venv)
```

**Do not** choose **Existing Jupyter Server**.

---

### Step 8: Test

Run:

```python
print("Hello Python")
```

You should get:

```
Hello Python
```

---

### If `python` is not recognized

Run:

```cmd
python --version
```

or

```cmd
py --version
```

If either command fails, Python is not installed correctly or isn't in your PATH.

Please run these commands in the VS Code terminal and share the output:

```cmd
python --version
py --version
where python
where py
```

I'll tell you the exact next step based on the results.
