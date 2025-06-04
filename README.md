# 2025-NYCU-Edgeai-final


## 專案簡介
本專案為 Edge AI 期末專案，主要目的是載入 ExLlamaV2 模型，並進行文本生成、推論效能測試（Throughput）、以及困惑度（Perplexity, PPL）評估。

## 主要功能
- 載入 ExLlamaV2 Q4 量化模型
- 使用自訂 `generate` 函數進行文本生成
- 以 WikiText-2 資料集評估模型困惑度（PPL）
- 計算推論 Throughput（每秒生成 token 數）
- 將結果輸出至 `19.csv`

## 執行方式

1. **安裝依賴套件**
   ```
   pip install -r req.txt
   ```

2. **準備模型**
   - 先前往https://huggingface.co/wei123602/exllama-Llama-3.2-3B-Instruct-3.0bpw 下載 ExLlamaV2 Q4 量化模型。
   - 將 ExLlamaV2 Q4 量化模型放置於 `/your_path/llama3.0bpw` 目錄下，或依需求修改 `result.py` 內的 `model_path`。

3. **執行主程式**
   ```
   python result.py
   ```

4. **輸出結果**
   - 結果會輸出於 `19.csv`，格式如下：
     | Id | value      |
     |----|------------|
     | 0  | PPL        |
     | 1  | Throughput |

## 主要檔案說明

- [`result.py`](result.py)：主程式，包含模型載入、生成、效能與困惑度評估邏輯。
- [`req.txt`](req.txt)：Python 依賴套件列表。
- [`19.csv`]：程式執行後自動產生，紀錄 PPL 與 Throughput。

## 參考
- [ExLlamaV2](https://github.com/turboderp/exllamav2)
- [WikiText-2 dataset](https://huggingface.co/datasets/wikitext)