<h1 align="center">Roland Keszi</h1>

<p align="center">
  <b>Data science · NLP & LLM evaluation · Market and opinion research</b><br>
  KROLIFY Research Institute · Hungary
</p>

<p align="center">
  <a href="https://krolify.hu"><img alt="Website" src="https://img.shields.io/badge/krolify.hu-research-0969da?style=flat-square&logo=googlechrome&logoColor=white"></a>
  <a href="https://krolify.hu/aktualis-kutatasok"><img alt="AI research" src="https://img.shields.io/badge/AI%20research-9%20topics-8250df?style=flat-square&logo=readthedocs&logoColor=white"></a>
  <a href="https://rolandkeszi-sentiment-usair.streamlit.app"><img alt="Live demo" src="https://img.shields.io/badge/live%20demo-Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white"></a>
  <a href="https://www.linkedin.com/company/krolify-research-institute/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-KROLIFY-0A66C2?style=flat-square&logo=linkedin&logoColor=white"></a>
</p>

---

### About me

- I combine **classical survey and market research methodology** with **modern machine learning and LLMs**.
- My current focus is **evaluating language models** on real text: how well they reproduce human labels, where they fail, and what that costs.
- I care about **reproducible, honest evaluation**: fixed samples, standard metrics, confusion matrices and a qualitative look at every error.
- I put results in front of people with **interactive dashboards** (Streamlit, Plotly) and my research site, [krolify.hu](https://krolify.hu).

---

### Featured: from lexicons to frontier LLMs — one sentiment task, 12 models

I benchmarked four generations of NLP on the same job: classifying IMDb movie reviews as positive or negative.

<p align="center">
  <img src="assets/sentiment-benchmark.svg" alt="Bar chart of sentiment accuracy on IMDb reviews. LLM zero-shot: GPT-5.3 Instant 96.9%, Claude Haiku 4.5 96.2%, Claude Sonnet 4.6 96.1%, GPT-4.1 mini 95.8%, Gemini 2.5 Flash-Lite 94.5%, Gemini 2.5 Flash 93.4%. Fine-tuned BERT 90.5%. Deep learning with GloVe: LSTM 86.8%, CNN 85.0%, simple NN 74.6%. Lexicon: VADER 69.9%, TextBlob 69.0%." width="100%">
</p>

| Approach | Model | Test set | Accuracy | Precision | Recall | F1 |
|---|---|---:|---:|---:|---:|---:|
| LLM, zero-shot | **GPT-5.3 Instant** | 1,000 | **0.969** | 0.963 | 0.973 | **0.968** |
| LLM, zero-shot | Claude Haiku 4.5 | 1,000 | 0.962 | 0.945 | **0.977** | 0.961 |
| LLM, zero-shot | Claude Sonnet 4.6 | 1,000 | 0.961 | 0.947 | 0.973 | 0.960 |
| LLM, zero-shot | GPT-4.1 mini | 1,000 | 0.958 | 0.954 | 0.958 | 0.956 |
| LLM, zero-shot | Gemini 2.5 Flash-Lite | 998 | 0.945 | 0.953 | 0.931 | 0.942 |
| LLM, zero-shot | Gemini 2.5 Flash | 634¹ | 0.934 | **0.958** | 0.910 | 0.933 |
| Fine-tuned transformer | BERT-base-uncased (9,600 training reviews, 2 epochs) | 1,200 | 0.905 | 0.887 | 0.928 | 0.907 |
| Deep learning + GloVe | LSTM | 10,000 | 0.868 | — | — | — |
| Deep learning + GloVe | CNN | 10,000 | 0.850 | — | — | — |
| Deep learning + GloVe | Simple neural network | 10,000 | 0.746 | — | — | — |
| Lexicon | VADER | — | 0.699 | 0.651 | 0.860 | 0.741 |
| Lexicon | TextBlob | — | 0.690 | 0.626 | 0.947 | 0.754 |

<sub>Precision, recall and F1 are for the positive class. ¹ Gemini 2.5 Flash returned a valid label for only 634 of 1,000 reviews because of API errors, so its scores are not directly comparable. The approaches use different test sets, so compare models within the same group.</sub>

**What the numbers say**

- **LLMs win without any training data.** Every zero-shot LLM beat a fine-tuned BERT by 3–6 percentage points.
- **A bigger model is not automatically better.** Claude Haiku 4.5 matched Claude Sonnet 4.6 (96.2% vs 96.1%) at a fraction of the cost.
- **Lexicons are biased toward "positive".** TextBlob's recall is 0.95, but its precision is only 0.63.
- **LSTM generalises best of the classic networks.** Its train–test gap is 1.1 points, against about 10 points for the CNN and the simple network.

📂 Notebooks: [rolandkeszi/TomegerzelemDetektalas](https://github.com/rolandkeszi/TomegerzelemDetektalas)

---

### Projects

| Project | What it does | Stack |
|---|---|---|
| 🤖 [**LLM vs. classical sentiment benchmark**](https://github.com/rolandkeszi/TomegerzelemDetektalas) | The 12-model comparison above. It covers prompt-based labelling through the OpenAI, Anthropic and Gemini APIs, BERT fine-tuning, CNN and LSTM networks on GloVe embeddings, and lexicon baselines. Each model gets confusion matrices and an error analysis. | Python, Hugging Face Transformers, Keras, scikit-learn |
| ✈️ [**US airline tweets: sentiment dashboard**](https://github.com/rolandkeszi/USAir) · [**live**](https://rolandkeszi-sentiment-usair.streamlit.app) | An interactive dashboard of about 14,500 tweets about six US airlines. It shows the sentiment split per airline, a tweet map with an hour-of-day filter, and word clouds per sentiment. | Streamlit, Plotly, pandas |
| 📈 [**Labour-market time series from the BLS API**](https://github.com/rolandkeszi/BLS_EmploymentData-Retrieval-from-API-with-R-) | Pulls US employment data from the Bureau of Labor Statistics API and charts the employment shock of COVID-19. | R, REST API |
| 🔬 [**AI research topics at KROLIFY**](https://krolify.hu/aktualis-kutatasok) | Summaries, charts and key figures on nine applied AI areas. These include text mining, network analysis, process mining, deep learning, image recognition, optimisation and Big Data. | Research write-ups |

---

### Toolbox

**Languages & data**<br>
<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"> <img alt="R" src="https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white"> <img alt="pandas" src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white"> <img alt="NumPy" src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white"> <img alt="SPSS" src="https://img.shields.io/badge/IBM%20SPSS-052FAD?style=flat-square&logo=ibm&logoColor=white">

**Machine learning & NLP**<br>
<img alt="scikit-learn" src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white"> <img alt="Hugging Face" src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black"> <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"> <img alt="Keras" src="https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white"> <img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white">

**LLM APIs**<br>
<img alt="Anthropic Claude" src="https://img.shields.io/badge/Claude%20API-191919?style=flat-square&logo=anthropic&logoColor=white"> <img alt="OpenAI" src="https://img.shields.io/badge/OpenAI%20API-412991?style=flat-square&logo=openai&logoColor=white"> <img alt="Google Gemini" src="https://img.shields.io/badge/Gemini%20API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white">

**Visualisation & apps**<br>
<img alt="Streamlit" src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white"> <img alt="Plotly" src="https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white"> <img alt="Matplotlib" src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square"> <img alt="Jupyter" src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white"> <img alt="Google Colab" src="https://img.shields.io/badge/Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white">

---

### How I work

1. **Same sample for every model.** I draw a fixed random sample with a seed, so model differences are not sampling noise.
2. **Standard metrics, every time.** I report accuracy, precision, recall, F1 and confusion matrices, plus the number of valid responses when an API fails.
3. **I read the errors.** Every misclassified review is listed and inspected. Irony, mixed reviews and plot summaries are where models break.
4. **No secrets in code.** API keys live in Colab Secrets or environment variables, never in notebooks.

---

<details>
<summary><b>🇭🇺 Magyarul</b></summary>
<br>

A klasszikus kérdőíves piac- és közvélemény-kutatás módszertanát kötöm össze a gépi tanulással és a nagy nyelvi modellekkel. Jelenleg nyelvi modellek értékelésével foglalkozom: azt vizsgálom, mennyire pontosan adják vissza az emberi címkéket, hol hibáznak, és ez mennyibe kerül.

Kiemelt projektem egy 12 modellt összehasonlító szentimentelemzés. Lexikon alapú módszereket (TextBlob, VADER), neurális hálókat (egyszerű háló, CNN, LSTM), finomhangolt BERT-et és zero-shot LLM-eket (GPT, Claude, Gemini) vetettem össze ugyanazon az IMDb-feladaton. A legjobb pontosságot, 96,9%-ot, a GPT-5.3 Instant érte el, és minden LLM jobb volt a finomhangolt BERT-nél.

További mesterséges intelligencia alapú kutatásaink: [krolify.hu/aktualis-kutatasok](https://krolify.hu/aktualis-kutatasok)

</details>

---

<p align="center">
  <sub>Open to research collaborations on LLM evaluation, text analytics and survey data. Reach me via <a href="https://krolify.hu">krolify.hu</a>.</sub>
</p>
