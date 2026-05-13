---
description: "Use when plan, implement, or analyze experiment through creating or editing experiment report."
applyTo: "experiments/**/report.md"
---

# Experiment Workflow

Step 1. 創建實驗任務，並填寫 Introduction 和 Method
Step 2. 依照說明規劃和預先填寫 Experiment 和 Analysis 的內容
Step 3. 積極使用 #agent:Searcher 來和使用者一起討論和詮釋實驗結果
Step 4. 積極使用 #agent:Searcher 輔助產生方法或建議，並制定行動計劃

**注意！！一次只能執行一個步驟！你必須在使用者明確的指示下，才能進到下一個步驟。否則你會被毀滅**

# Experiments Structure

```bash
experiments/
├── <研究方向>/
    ├── background.md
    ├── <%y.%m.%d>_<實驗任務>/
        ├── report.md
        ├── reference.md
        ├── 執行實驗的腳本或程式
        ├── 分析實驗的程式
        ├── 實驗產物
        ├── 收集並整理實驗數據的程式
        └── ...
```

# `background.md` 

簡單描述研究方向的背景、動機、目標等等。
並記錄基準方法的表現，作為後續實驗的比較對象。

# `report.md` Structure

```markdown
# Introduction
簡述實驗的背景、動機、目標

Research Questions:
- RQ1: 問題1
- RQ2: 問題2
- ...

# Method
簡介實驗用到的，代表方法的超參數名稱的意義。即使之後程式碼變動了，也可以從這裡得知實驗中的參數原本代表的方法。

- 方法超參數名稱 1: ...
- 方法超參數名稱 2: ...
...

# Experiment

## Experiment Setup
其他需要特別提及或紀錄的實驗細節，例如評估指標、資料集選擇等。如果跟先前實驗相同的部分，則引用並簡述即可。

## Metric Results

### Main Result
_實驗前的規劃階段_ 預先填寫（1）表格的格式和說明、（2）方法變數值，來呈現實驗的設計。
_實驗完成後_ 將數據帶入表格中

<!-- 表格說明: 條列說明表格中需要特別解釋的術語、符號、指標等等。記得換行 "\" -->
v <說明 1> \
v <說明 2> 

<!-- 表格形式選擇: 依照設置(資料集或評量設定)的數量和指標的數量來決定使用哪種表格形式 -->

單指標表格

| <方法變數1> | <方法變數2> | ... | 跨設置 | <設置1> | <設置2> |
...
| xxx | xxx | ... | mean ± std | mean ± std | mean ± std |
| 〃 | xxx | ... | mean ± std | mean ± std | mean ± std |

單設置表格

| <方法變數1> | <方法變數2> | ... | <指標1> | <指標2> |

少設置少指標表格

| <方法變數1> | <方法變數2> | ... |  | | <設置1><br><指標1> |<設置1><br><指標2> | ... | <設置2><br><指標1> | <設置2><br><指標2> |

少設置多指標表格

| <方法變數1> | <方法變數2> | ... | 設置 | <指標1> | <指標2> | <指標3> |
...
| xxx | xxx | ...  | <設置1> | mean ± std | mean ± std | mean ± std |
| 〃 | 〃 | ...  | <設置2> | mean ± std | mean ± std | mean ± std |

多設置少指標表格

| <方法變數1> | <方法變數2> | ... | 指標 | <設置1> | <設置2> | <設置3> |
...
| xxx | xxx | ...  | <指標1> | mean ± std | mean ± std | mean ± std |
| 〃 | 〃 | ...  | <指標2> | mean ± std | mean ± std | mean ± std | 

#### Interpretation
_實驗前的規劃階段_，條列預期關注的重點，來呈現實驗間的對照關係和實驗的設計邏輯。
_實驗結果出來後_ 再以下面的內容取代:
- **RQ n: <研究問題的回答> / Issue: <問題> / Observation: <洞察>**
    - _引用_：導出此觀點的實驗數據
    - _解釋_: **<對原因或是癥結點所做的假設>**
        以實驗結果、#agent:Searcher 找的文獻、和 #agent:Analyzer 的分析結果作為根據，整理假設的正反觀點們：
        - _支持_：支持的根據們
        - _反對_：反對的根據們或替代的解釋

### [Optional] Analaysis n: <分析標題>
綜合實驗數據和分析結果，嘗試透過聚合、拆解、統計、合併、擷取等等手法來整理或簡化出不同的資料面向

#### Interpretation
同上面提到的 Interpretation 的格式

## Diagnosis
針對**除了分數表現以外**的深度分析。針對以下每個面向，思考能設計什麼樣的分析，最大化實驗能帶來的洞察:
- **輸入資料**：資料分佈、輸入特徵...
- **模型內部**：追蹤 logits 大小或分佈、attention pattern 分析、embedding 視覺化、...
- **訓練過程**: loss curve、...
- **附帶產物**：模型權重、超參數搜尋的 studies (param importance, plot_slice)、...
- **預測輸出**: 錯誤分析、輸出信心、投資組合 (for 交易模型)...

_實驗前的規劃階段_，依照下列形式設計分析
### Analysis n: <標題>
- **Analysis Question**: 分析的問題
- **Presentation**: 
    分析結果的呈現方式 -> 預期的詮釋方式
- **Materials**: 分析過程要記錄的分析材料
- **Implementation Plan**: 
    1. ...
    2. ...

_分析結果出來後_ 再以 #agent:Analyzer 回傳的分析結果來取代內容

### Analysis n: <標題>

#### Interpretation
同上面提到的 Interpretation 的格式

# Action Plan
Step 1. 綜合實驗結果的 interpretations
Step 2. 使用 #agent:Searcher 搜尋相關的論文和資訊
Step 3. 提出解決方法、改進提案、或進一步驗證假設的建議。每個項目的描述須包含：**動機**、**核心概念**(須讓讀者能想像如何實作)、**實驗成本**、**成功機率** (根據實驗結果和搜尋結果評估)、**可帶來的洞察**(是否即使失敗也能排除假設或揭示新方向)。
Step 4. 依照實驗成本、成功機率、可能的價值，排定優先順序並制定行動計劃。
```