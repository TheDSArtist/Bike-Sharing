# Setup Guide: Repository Clone, UV Environment, and Jupyter Kernel

This guide outlines the steps to clone the required repository, set up a highly efficient virtual environment using the **uv** package manager, and launch the `submission.ipynb` file using the correct Python kernel.

---

## Prerequisites

- **Git**: You must have Git installed on your system to clone the repository.
- **uv**: The uv package manager must be installed. If you don't have it, you can install it using pip (or follow the official uv documentation for a standalone installation):

```bash
pip install uv
# OR if you prefer to install it globally without pip
# curl -LsSf https://astral.sh/uv/install.sh | sh
```

---

## Step 1: Clone the Repository

First, use Git to clone the repository to your local machine. Replace `[REPOSITORY_URL]` with the actual URL of your Git repository.

```bash
# Clone the repository (e.g., from GitHub, GitLab, or other host)
git clone [REPOSITORY_URL]

# Change into the cloned directory
cd [repository-name]
```

---

## Step 2: Create and Activate the Virtual Environment with uv

We will use **uv** to create a lightweight and isolated virtual environment specifically for this project.

### Create the environment:

```bash
uv venv
```

This command creates a new virtual environment named `.venv` in the current directory.

### Activate the environment:

- **On macOS/Linux**:
```bash
source .venv/bin/activate
```

- **On Windows (Command Prompt)**:
```bash
.venv\Scripts\activate.bat
```

- **On Windows (PowerShell)**:
```bash
.venv\Scripts\Activate.ps1
```

You should see `(.venv)` prepended to your command line prompt, indicating the environment is active.

---

## Step 3: Install Dependencies using uv sync

The `uv sync` command reads your project's dependency files (`pyproject.toml` or `requirements.txt`) and ensures the virtual environment (`.venv`) matches the exact state defined in those files.

```bash
# Synchronize the virtual environment with dependencies defined in the project files
uv sync
```

**Note**: `uv sync` automatically detects and uses standard dependency files (`pyproject.toml`, `requirements.txt`, etc.) in the current directory.

---

### Important:

You will at minimum need to install **jupyter** and **ipykernel** to run the notebook and manage the kernel. If these are not listed in your project dependency files, you must install them separately:

```bash
uv pip install jupyter
```
