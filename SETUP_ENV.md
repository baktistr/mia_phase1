# Python Environment Setup for MIA Phase 1

## ✅ What's Already Done
1. Created virtual environment at `.venv`
2. Installed `ipykernel` and `jupyter`
3. Registered kernel as **"Python (MIA Phase1 .venv)"**

## 🎯 How to Use the Notebook in VS Code

### Step 1: Select the Kernel
1. Open `MIA_phase1.ipynb` in VS Code
2. Look at the top-right corner of the notebook
3. Click on "Select Kernel" (or the current kernel name)
4. Choose **"Python (MIA Phase1 .venv)"** from the list
   - If you don't see it, click "Select Another Kernel..." → "Jupyter Kernel..." → "Python (MIA Phase1 .venv)"

### Step 2: Install Project Dependencies
Run this in a terminal (WSL):
```bash
cd "/mnt/c/Users/adhit/OneDrive/Documents/CMU/Fall 2025/17-731 Foundations of Privacy/project/Project_phase1"
.venv/bin/pip install -r requirements.txt
```

**Note:** This will install heavy packages like PyTorch, transformers, etc. It may take 5-15 minutes.

### Step 3: Verify Installation
Add and run this cell in your notebook:
```python
import sys
print("Python executable:", sys.executable)
print("Python version:", sys.version)

# Check key packages
import torch
import transformers
print(f"PyTorch version: {torch.__version__}")
print(f"Transformers version: {transformers.__version__}")
print(f"CUDA available: {torch.cuda.is_available()}")
```

## 🔧 Common Issues & Solutions

### Issue: "No kernel found" or kernel not showing
**Solution:**
1. Reload VS Code window (Ctrl+Shift+P → "Developer: Reload Window")
2. Make sure you have the "Jupyter" extension installed in VS Code
3. Try selecting kernel again

### Issue: Packages not found when running cells
**Solution:**
Make sure you selected the correct kernel **"Python (MIA Phase1 .venv)"**, not the system Python.

### Issue: Torch installation fails or CUDA errors
**Solution for WSL with NVIDIA GPU:**
```bash
# Install PyTorch with CUDA support (adjust CUDA version if needed)
.venv/bin/pip install torch==2.8.0 --index-url https://download.pytorch.org/whl/cu121
```

**Solution for CPU-only:**
```bash
# Edit requirements.txt and change torch line to:
# torch==2.8.0+cpu
# Then run:
.venv/bin/pip install -r requirements.txt
```

## 📦 Package List
Your environment includes:
- torch (2.8.0) - Deep learning framework
- transformers (4.56.2) - Hugging Face transformers
- datasets (4.1.1) - Dataset loading
- scikit-learn (1.7.2) - ML metrics
- matplotlib - Plotting
- numpy (1.26.4) - Numerical computing
- And more...

## 🚀 Quick Start Commands

### Activate environment (in terminal):
```bash
cd "/mnt/c/Users/adhit/OneDrive/Documents/CMU/Fall 2025/17-731 Foundations of Privacy/project/Project_phase1"
source .venv/bin/activate
```

### Install all dependencies:
```bash
.venv/bin/pip install -r requirements.txt
```

### Check installed packages:
```bash
.venv/bin/pip list
```

### Update a specific package:
```bash
.venv/bin/pip install --upgrade <package-name>
```

## 💡 Tips
- VS Code's Jupyter support is built-in - no need to run `jupyter notebook` separately
- The kernel runs in the background when you execute cells
- Use Shift+Enter to run a cell and move to the next one
- The `.venv` folder is your isolated environment - don't delete it!
