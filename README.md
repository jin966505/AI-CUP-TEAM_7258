環境

- 作業系統：Windows 11 專業版
- 語言：Python (版本 3.11.12)
- 文字編輯器：Visual Studio Code (版本 1.100.2) / Google Colab (來源: [https://colab.research.google.com/](https://colab.research.google.com/))


score

![螢幕擷取畫面 2025-06-16 194427](https://github.com/user-attachments/assets/fcf4882e-1bde-46e4-ac56-d2c7694bdde9)

套件（函式庫）

- [Transformers 套件 (版本 4.49.0)](https://pypi.org/project/transformers/)
- [Torch 套件 (版本 2.6.0)](https://pypi.org/project/torch/)
- [pandas 套件 (版本 2.2.3)](https://pypi.org/project/pandas/)
- [openai 套件 (版本 1.86.0)](https://pypi.org/project/openai/)


預訓練模型：  
本專案使用 OpenAI 的 gpt-3.5-turbo 模型，該模型為一經過大規模語料預訓練，並針對對話與指令任務微調的封裝式語言模型。雖無法存取原始權重，但能透過 prompt 設計精準控制輸出行為，其行為已整合預訓練與後續強化學習成果，可作為推論任務之用。

安裝所需套件
請先安裝 Whisper large v3 及本專案需求的其他套件


比賽流程執行

(1) 訓練模型與輸出文字
執行 AICUP2025_Phase1_Dataset.ipynb

匯入 __pycache__ 相關檔案

匯入競賽官方給的訓練集Training_Dataset_Phase1_Sample

將zip_path後的檔名改成此檔案名稱

會自動使用 Whisper large v3 進行語音訓練

完成後會產生：

訓練後模型壓縮檔（whisper-large-v3）

任務一的答案文字（task1_answer）

(2) 產生時間戳
執行 wahf2ct_colab.ipynb

需將 whisper-large-v3 壓縮檔放入相同資料夾

會輸出 task1 的時間戳（task1_answer_timestamps）

(3) 輸出最終答案
執行 test6.ipynb

匯入 task1_answer 和 task1_answer_timestamps

產生符合競賽格式的最終答案（test2）
