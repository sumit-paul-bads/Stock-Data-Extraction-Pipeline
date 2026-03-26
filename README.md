# 📈 Historical Stock Data Extraction & Preprocessing Pipeline

## 🎥 Project Presentation
[![Watch the Presentation]

https://drive.google.com/file/d/1yjch4hKJNEua2pPgl8Rnlbf-s8vioH_k/view?usp=sharing
> **Note:** Click the badge above to watch the full video presentation of this project.

## 📊 Project Slides (Gamma App)
You can view the interactive slide deck for this project here: 
[View Full Presentation on Gamma]
https://gamma.app/docs/Historical-Stock-Data-Extraction-Preprocessing-hgoiinf10oq4cot

---

## 📌 Project Objective
This project establishes an automated data engineering pipeline to extract, clean, and verify historical stock market data from the **NSE (National Stock Exchange)** and **BSE (Bombay Stock Exchange)** using the Alpha Vantage API. 

The resulting datasets are structured specifically for **Time-Series Forecasting** and **Machine Learning** models (e.g., LSTM, Linear Regression).

---

## 🚀 Key Technical Features

### 1. Strategic API Pivot (NSE Proxy)
During development, the direct Alpha Vantage NSE endpoint was identified as a premium-tier feature. To maintain a free, open-source workflow, I utilized **HDB (HDFC Bank ADR)** as a high-correlation proxy for the NSE. This ensured the pipeline remained functional while providing accurate market signals.



### 2. Time-Series Continuity (Reindexing)
Financial markets are non-continuous (weekends/holidays). For deep learning models to function correctly, a continuous timeline is required. 
* **Process:** Created a custom `pd.date_range` from start to end.
* **Result:** Successfully expanded the dataset from 100 trading days to a complete calendar sequence.

### 3. Data Imputation (Forward Fill)
To handle the "gaps" created by market closures, I implemented a **Forward Fill (ffill)** strategy. This carries the last known closing price forward, ensuring **0% Null Values** without introducing synthetic noise into the data.



---

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Libraries:** Pandas (Data Manipulation), Requests (HTTP/API calls)
* **API:** Alpha Vantage

---

## ⚙️ Setup & Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Stock-Data-Extraction-Pipeline.git](https://github.com/YOUR_USERNAME/Stock-Data-Extraction-Pipeline.git)
