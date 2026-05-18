# Introduction
<簡述實驗的背景、動機、目標>

Research Questions:
- RQ1: ...
- RQ2: ...

# Method
<!-- 
列出實驗中代表方法的超參數名稱與其意義。
即使之後程式碼變動了，也可以從這裡得知實驗中的參數原本代表的方法。
-->

- `<超參數名稱1>`: <!-- 意義說明 -->
- `<超參數名稱2>`: <!-- 意義說明 -->

# Experiment

## Experiment Setup
<!--
記錄需要特別提及的實驗細節：
- 評估指標
- 資料集選擇
- 訓練/測試切分方式
- 其他重要的實驗條件

若與先前實驗相同，可引用並簡述。
-->

## Performance
<!-- 可有一到多個圖表 -->
<圖表與詮釋。遵循格式[table-chart-template.md](./assets/table-chart-template.md)>

# Diagnosis
<!--
針對除了分數表現以外的深度分析。
針對以下每個面向，思考能設計什麼樣的分析，最大化實驗能帶來的洞察：
- 輸入資料：資料分佈、輸入特徵分析
- 模型內部：logits 分佈、attention pattern、embedding 視覺化
- 訓練過程：loss curve、學習率曲線
- 附帶產物：模型權重、超參數搜尋的 studies (param importance, plot_slice)
- 預測輸出：錯誤分析、輸出信心、投資組合分析
-->

## Diagnosis: <標題>
<Analysis Question: 這個分析要回答的問題>

<!--【實驗前規劃階段，依照下列形式設計分析】-->
- **Presentation**: <呈現方式（例如：折線圖、熱力圖、表格）→ 預期的詮釋方式>
- **Materials**: <分析過程需要記錄的材料（例如：模型權重、預測輸出、loss 曲線）>
- **Implementation Plan**:
  1. ...
  2. ...

<!--【分析完成後】圖表可為一或多個-->
<圖表與詮釋。遵循格式[table-chart-template.md](./assets/table-chart-template.md)>

# Conclusion
<!-- 綜合所有實驗結果、觀察、詮釋，回答研究問題 -->

## RQ1：<問題>
**答：<答案>**
<引用的實驗結果、推測的原因或癥結點、支持的根據、反對的根據>

# Action Plan

## Action 1: <!-- 標題 -->

- **Motivation**: <!-- 為什麼要做這件事 -->
- **Core Concept**: <!-- 核心想法，需讓讀者能想像如何實作 -->
- **Implementation**: <!-- 實作方式 -->
- **Experiment Cost**: <!-- 預估實驗成本（資料量、訓練時間、人力） -->
- **Success Probability**: <!-- 根據實驗結果和搜尋結果評估成功機率 -->
- **Potential Insights**: <!-- 能夠帶來的驗證或洞察效益 -->
