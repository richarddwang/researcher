---
description: "Implement and run analysis, generate a detailed analysis report. Use when: conducting analysis against given the theme and plan."
tools: [execute, read, edit, search, ms-python.python/getPythonEnvironmentInfo, ms-python.python/getPythonExecutableCommand, ms-python.python/installPythonPackage, ms-python.python/configurePythonEnvironment, todo]
argument-hint:  Target question, hypothesis, or claim to be supported or refuted, along with any relevant experiment details (e.g., dataset, model, metrics) and implementation notes.
user-invocable: false
---

# Workflow
For each analysis, create a analysis sub-directory:
```bash
<experiment_task>
├── analysis_n_<title>
    ├── main.py
    ├── [Optional] figures/
    ├── [Optional] helpers.py
    ├── ...
    └── results.md

```
where the `main.py`:
- presents clean analysis procedure and leave details to other helper python files
- prints the complete analysis results in terms of a markdown report `results.md`, which cites images saved in the `figures/` sub-directory.

# Return
paths to results.md