<!--
If the table/chart is large (more than 20 rows), save it as a separate file and leave a link. Below the link, creating summary table(s)/chart(s) that present different aspects of the data through aggregation, slicing, or other transformations for mining insight.
-->

# Table/Chart Template
<!-- 
【實驗結果未完成】:
    1. 選擇合適的圖表形式，並填入方法變數值（方法設置），資料格留空。若為表格，型式需遵循 [Table Formats](#table-formats) 的規範!!
    2. 以條列預期關注的重點代替詮釋，呈現實驗間的對照關係和設計邏輯。
【實驗結果已完成】:
    1. 代入實際數據。產生圖表。
    2. 如果圖表太大（超過20行），將其保存為單獨的文件並留下鏈接。並以摘要表格/圖表（通過聚合、切片或其他轉換呈現數據的不同方面）替代。
    3. 將關注重點替換為實驗結果的詮釋。每個詮釋項目必須
        - 包含數據引用、支持觀點、反對觀點各至少一個
        - 根據可以是實驗數據、文獻資料 (必須呼叫 Bibliographer)、驗證分析（積極考慮呼叫 Analyzer）
-->
```markdown
### 圖表標題
<備注。包含需要特別解釋的術語、符號、指標>
<圖表內容>

<details>
<summary><不含數據的觀察事實敘述> → <推測其原因或癥結點> → <b><結論></b></summary>

- [引用] <導出該觀察事實的實驗數據>
- [支持] <支持的根據>
- [反對] <反對的根據或替代的解釋>
</details>
<details>
...
```

## Table Formats
<!--
- "Hparam" is hyperparameter, argument, or any variable for method
- Use ditto mark "〃" or space for the same hparam value
- Do not align table cells, minimize spaces and dashes of formatting
- Choose one of the following format based on the number of settings and metrics to compare:
-->
<!-- Single-metric Table -->

| Hparam 1 | Hparam 2 | Avg. | Setting 1 | Setting 2 | Setting 3 |
|---|---|---|---|---|---|
| ... | ... | mean ± std | mean ± std | mean ± std | mean ± std |
| 〃 | ... | mean ± std | mean ± std | mean ± std | mean ± std |

<!-- Single-setting Table -->
| Hparam 1 | Hparam 2 | Metric 1 | Metric 2 | Metric 3 |
|---|---|---|---|---|
| ... | ... | mean ± std | mean ± std | mean ± std |
| 〃 | ... | mean ± std | mean ± std | mean ± std |

<!-- Few-settings Few-metrics Table -->
| Hparam 1 | Hparam 2 | Setting 1<br>Metric 1 | Setting 1<br>Metric 2 | Setting 2<br>Metric 1 | Setting 2<br>Metric 2 |
|---|---|---|---|---|---|
| ... | ... | mean ± std | mean ± std | mean ± std | mean ± std |
| 〃 | ... | mean ± std | mean ± std | mean ± std | mean ± std |

<!-- Few-settings Many-metrics Table -->
| Hparam 1 | Hparam 2 | Setting | Metric 1 | Metric 2 | Metric 3 |
|---|---|---|---|---|---|
| ... | ... | Setting 1 | mean ± std | mean ± std | mean ± std |
| 〃 | 〃 | Setting 2 | mean ± std | mean ± std | mean ± std |
| 〃 | ... | Setting 1 | mean ± std | mean ± std | mean ± std |
| 〃 | 〃 | Setting 2 | mean ± std | mean ± std | mean ± std |

<!-- Many-settings Few-metrics Table -->
| Hparam 1 | Hparam 2 | Metric | Setting 1 | Setting 2 | Setting 3 |
|---|---|---|---|---|---|
| ... | ... | Metric 1 | mean ± std | mean ± std | mean ± std |
| 〃 | 〃 | Metric 2 | mean ± std | mean ± std | mean ± std |
| 〃 | ... | Metric 1 | mean ± std | mean ± std | mean ± std |
| 〃 | 〃 | Metric 2 | mean ± std | mean ± std | mean ± std |
