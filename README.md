# 📞 Call Quality Analyzer  

A **Google Colab-ready Python project** that analyzes sales call recordings and extracts key metrics to evaluate call quality.  

This project was built as part of an assignment for a **Voice AI startup**.  

---

## 🚀 Features (Assignment Requirements)

- ✅ **Talk-time ratio** – percentage each speaker spoke  
- ✅ **Number of questions asked** – using `?` and WH-word detection  
- ✅ **Longest monologue duration** – longest continuous speech span  
- ✅ **Call sentiment** – positive / negative / neutral (HuggingFace sentiment pipeline)  
- ✅ **One actionable insight** – rule-based suggestions  
- ✅ **Bonus** – attempts to identify the likely **Sales Rep vs Customer**  
- ✅ **Handles poor audio quality** – audio normalized to 16kHz mono  
- ✅ **Fast (<30s runtime)** – uses `faster-whisper (tiny)` model, optimized for Colab free tier  
- ✅ **Saves results in `call_report.txt`** – easy to download final analysis  

---

## 📂 Example Output

After running the notebook, you get a `call_report.txt` file like:

```
📞 Call Quality Report
----------------------------------------
Talk-time ratio: {'Speaker_1': 68.5, 'Speaker_2': 31.5}
Number of questions asked: 4
Longest monologue duration: 22.4 seconds (by Speaker_1)
Overall sentiment: POSITIVE (0.93)
Actionable insight: Speaker_1 dominates the call (68.5%). Suggest: ask more questions and pause to listen.
Likely Sales Rep: Speaker_1
```

You can download the report from Colab’s left **Files panel**, or with:

```python
from google.colab import files
files.download("call_report.txt")
```

---

## 🛠 How to Run

1. Open this notebook directly in Colab 👉  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adityaraj161616/callqualityanalyzer/blob/main/Call_Quality_Analyzer_Assignment_Final.ipynb)

2. In Colab:  
   - Go to **Runtime → Change runtime type → GPU** (recommended)  
   - Then **Runtime → Run all**  

3. Wait ~30 seconds for analysis to complete.  
4. Download `call_report.txt` for the summary report.  

---

## ⚙️ Tech Stack

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) & [pytube](https://pytube.io) – download YouTube audio  
- [pydub](https://github.com/jiaaro/pydub) – audio preprocessing & normalization  
- [faster-whisper](https://github.com/guillaumekln/faster-whisper) – ASR transcription (tiny model)  
- [HuggingFace Transformers](https://huggingface.co/docs/transformers) – sentiment analysis  
- [PyTorch](https://pytorch.org) – GPU acceleration in Colab  

---

## 📌 Notes
- Default test file: [YouTube – Sales Call Recording](https://www.youtube.com/watch?v=4ostqJD3Psc)  
- If YouTube download fails, you can manually upload an MP3 in Colab.  
- This notebook prioritizes **speed & reproducibility**. For production, upgrade diarization (e.g., `pyannote`) and use a larger Whisper model.  

---

✨ Made by **Aditya Raj (CSE 2026)**  
