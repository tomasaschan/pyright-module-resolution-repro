# Repro for Pyright module resolution issue

1. Install both the Python extension (`ms-python.python`) and the Pyright extension (`ms-pyright.pyright`). Reload window if required.

1. Create a virtual environment in this folder:

   ```sh
   virtualenv .venv
   ```

1. Select the Python interpreter in that virtual environment (Command Palette>`Python: Select Interpreter`>`.venv/bin/python`)

1. Open [`src/module_b/__init__.py`](/src/module_b/__init__.py).

1. Pyright reports `Import "module_a" could not be resolved`, while the Python extension has no trouble resolving the module.

1. Optional: Change the import to `from src.module_a import foo`. Now Pyright finds the module, but the Python extension does not.

**How do I configure Pyright to use the same module resolution roots as the Python extension does?**
