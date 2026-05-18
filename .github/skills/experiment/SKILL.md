---
name: experiment
description: "Design, diagnose, and interpret experiments and plan actions through a structured report.md. Use when: creating a new experiment, writing or editing experiment report, planning experiment design, filling in report.md, interpreting experiment results, analyzing performance, generating action plans, or discussing findings."
argument-hint: "Describe the experiment goal, or sections to complete or discuss."
---
# Experiment File Structure

```bash
experiments/
├── <研究方向>/
  ├── background.md # 簡單描述研究方向的背景、動機、目標等等。並記錄基準方法的表現，作為後續實驗的比較對象。
  └── <YY.MM.DD>_<實驗任務>/
      ├── report.md # 實驗報告，使用 report-template.md 模板
      ├── reference.jsonl # 調研過程中找到的相關論文或網頁等等的紀錄
      ├── <experiment execution script(s)> # 執行實驗的腳本或程式
      ├── <experiment result collection script(s)> # 收集並整理實驗數據的程式
      ├── [Optional]logs/ # 實驗過程紀錄下的東西
      ├── [Optional]checkpoints/ # 模型權重
      ├── [Optional]outputs/ # 實驗產物
      └── analysis_.../ 
          ├── main.py # 清楚表達分析流程，將細節封裝到其他檔案。並產出（引用圖片的）文字報告
          ├── <util or helper script(s)>
          └── figures/ # 分析產生的圖
```
# Experiment Workflow

The lifecycle of research experiments through a structured `report.md`

## CRITICAL RULE

Execute a step only when the user explicitly instructs you to, **one step at a time**.

## Step 1 — Introduction and Method

1. Create the experiment directory with a `report.md`
2. Based on user's query, write **Introduction** to define the research task
3. Actively survey literature and ask user questions to brainstorm methods, then write them down in **Method**

**Stop — wait for explicit user instruction before advancing.**

## Step 2 — Plan Experiment and Diagnosis

1. Design **Experiment** and their relationship, and present them in pre-filled experiment results table followed by expected focusing points, according to the report template.
2. Plan **Diagnosis** in the format specified in the report template.

**Stop — wait for explicit user instruction before advancing.**

## Step 3 — Conduct Diagnosis and Interpret Results

1. Let `#agent:Analyzer` conduct **Diagnosis** and fill in results according to the report template.
2. Based on the diagnosis and experiment results, come up with observations and interpretations in format of interpretations template.
3. Use `#agent:Bibliographer` to find relevant literature or information, and `#agent:Analyzer` to verify hypotheses. Then update the interpretations.

**Stop — wait for explicit user instruction before advancing.**

## Step 4 — Answer Research Question(s)

1. Read all observations, interpretations from previous sections
2. Think step by step and summarize the answer(s) to the research question(s) in **Conclusion** section of the report.

**Stop — wait for explicit user instruction before advancing.**

## Step 5 — Propose and Sort Methods and Actions

1. Based on findings from Performance and Diagnosis sections, use `#agent:Bibliographer` to find relevant literature or information
2. Propose solutions, improvement suggestions, or further verification of hypotheses. Each item follows the format in report template.
3. Ask user questions to stimulate thinking and brainstorming
4. Prioritize actions by: (cost) × (success probability) × (potential value)

