

# 🧠 Hate Speech Detection with Deep Learning
This project explores how we can use deep learning to detect **hate speech** in text. We built and compared two models:
- A custom **LSTM-based model**
- A fine-tuned **BERT-based model**

Both models were trained on a balanced dataset of labeled sentences. Our goal was to see which model performs better .

---

## 🗂️ Dataset
We used the `HateSpeechDatasetBalanced.csv` file. It contains a roughly equal number of hate and non-hate samples, which makes training fairer and easier. No additional balancing was needed.

---

##  Models Overview

### 🔹 LSTM Model
- Embedding layer (300 dimensions)
- Dropout for regularization
- Bidirectional LSTM (128 hidden units)
- Attention layer
- Fully connected output layer

> Optimizer: **Adam**  
> Loss: **CrossEntropyLoss**

---

### 🔹 BERT Model
- Based on the pre-trained `bert-base-uncased`
- Added a classification layer on top
- Fine-tuned only the last 2 layers of BERT (others frozen)

> Optimizer: **AdamW**  
> Loss: **CrossEntropyLoss**

---

## 📈 Results at a Glance

| Model | Best Test Accuracy | Training Time | Total Parameters |
|-------|--------------------|----------------|------------------|
| LSTM  | 87.9%              | ~3 hours       | ~21 million      |
| BERT  | 90.1%              | ~10 hours      | ~14 million      |

✅ **BERT performed better**, but took longer to train  
⚡ **LSTM was faster**, but slightly less accurate

---

##  How to Run It Yourself

1. Open the notebook: `Test_HateSpeach.ipynb`
2. [Follow the Google Drive link](https://drive.google.com/drive/folders/14SVAWYF0mz62BXiEaqMHDvXliEaq-Wto?usp=sharing)  to download:
   - `FTBertTrained.pth`
   - `LSTMTrained.pth`
   - `HateSpeechDatasetBalanced.csv`
3. Upload the files into your environment
4. Run the cells:
   - **First cell** → test the LSTM model
   - **Second cell** → test the BERT model


---

## 📌 Conclusion
If you're looking for a **quick model**, LSTM does a solid job.  
If you want **best performance**, go with BERT — even if it takes longer.

There’s always a trade-off between **simplicity & speed** vs. **accuracy & complexity**.

---

## 📄 More Details?
Check out the full project report 👉 `final_project_report_deep_.pdf`  

---

