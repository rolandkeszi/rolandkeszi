<h1 align="center">Roland Keszi</h1>

<p align="center">
  <b>AI &amp; data science · LLM evaluation · NLP</b><br>
  Turning survey and text data into insight · Hungary
</p>

<p align="center">
  <a href="https://rolandkeszi.github.io"><img alt="Portfolio" src="https://img.shields.io/badge/portfolio-rolandkeszi.github.io-16181d?style=flat-square&logo=githubpages&logoColor=white"></a>
  <a href="#featured-from-lexicons-to-frontier-llms--one-sentiment-task-12-models"><img alt="LLM benchmark" src="https://img.shields.io/badge/LLM%20benchmark-12%20models-8250df?style=flat-square&logo=openai&logoColor=white"></a>
  <a href="https://rolandkeszi-sentiment-usair.streamlit.app/?lang=en"><img alt="Live demo" src="https://img.shields.io/badge/live%20demo-Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/rolandkeszi/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-Roland%20Keszi-0A66C2?style=flat-square&logo=linkedin&logoColor=white"></a>
  <a href="#projects"><img alt="Projects" src="https://img.shields.io/badge/projects-Python%20%7C%20R-0969da?style=flat-square&logo=github&logoColor=white"></a>
</p>

---

### About me

- I combine **classical survey and market research methodology** with **modern machine learning and LLMs**.
- My current focus is **evaluating language models** on real text: how well they reproduce human labels, where they fail, and what that costs.
- I care about **reproducible, honest evaluation**: fixed samples, standard metrics, confusion matrices and a qualitative look at every error.
- I turn results into **clear charts and interactive dashboards** (Streamlit, Plotly, ggplot2) that non-technical readers can act on.

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

📂 Notebooks: [rolandkeszi/llm-sentiment-benchmark](https://github.com/rolandkeszi/llm-sentiment-benchmark)

---

### Projects

<p>📂 <b>Full case studies with methods, results and explanations: <a href="https://rolandkeszi.github.io">rolandkeszi.github.io</a></b></p>

<table>
<tr>
<td width="50%" valign="top">

**⚡ [Estimating power plant output with regression models](https://github.com/rolandkeszi/power-plant-output-prediction)** · [**case study**](https://rolandkeszi.github.io/projects/power-plant.html)

<a href="https://rolandkeszi.github.io/projects/power-plant.html"><img src="https://raw.githubusercontent.com/rolandkeszi/power-plant-output-prediction/main/figures/pp_model_comparison.png" width="100%" alt="Test R² of the five regression models compared in the study"></a>

Linear, polynomial, lasso, ridge and neural network models were compared on 8,568 hours of plant operation. **An interpretable linear model (R² = 0.93)** was chosen and validated with 5-fold cross-validation and on an independent sample of 1,000 hours (F-test of residual variances, F = 1.016). Each extra °C of ambient temperature costs about 2 MW.

<sub>Python · scikit-learn · TensorFlow · IBM SPSS</sub>

</td>
<td width="50%" valign="top">

**✈️ [US airline tweets: sentiment dashboard](https://github.com/rolandkeszi/USAir)** · [**live demo**](https://rolandkeszi-sentiment-usair.streamlit.app/?lang=en)

<a href="https://github.com/rolandkeszi/USAir"><img src="https://raw.githubusercontent.com/rolandkeszi/USAir/main/assets/sentiment-by-airline.svg" width="100%" alt="Sentiment split per US airline"></a>

An interactive Streamlit dashboard of 14,640 labelled tweets. **63% of the tweets are negative**, and US Airways gets 8.4 negative tweets for every positive one. Customer service drives the most complaints.

<sub>Python · Streamlit · Plotly · pandas</sub>

</td>
</tr>
<tr>
<td width="50%" valign="top">

**🏥 [Patient pathways and hospital resources](https://github.com/rolandkeszi/hospital-process-mining)** · [**case study**](https://rolandkeszi.github.io/projects/process-mining.html)

<a href="https://rolandkeszi.github.io/projects/process-mining.html"><img src="https://raw.githubusercontent.com/rolandkeszi/hospital-process-mining/main/figures/09_bpmn.png" width="100%" alt="BPMN model of the patient pathway"></a>

Process mining of a hospital event log (100 patients, 690 events): care pathways, throughput times and staff workload. **DFG, Petri net, BPMN and heuristic net**, with the alpha, inductive and heuristic miners compared on fitness, precision, generalization and simplicity.

<sub>Python · PM4Py · Graphviz</sub>

</td>
<td width="50%" valign="top">

**📈 [The COVID-19 shock in the US labour market](https://github.com/rolandkeszi/bls-covid-labour-market)**

<a href="https://github.com/rolandkeszi/bls-covid-labour-market"><img src="https://raw.githubusercontent.com/rolandkeszi/bls-covid-labour-market/main/assets/covid-labour-market.svg" width="100%" alt="US unemployment, employment ratio and payrolls 2015-2026"></a>

An R pipeline on the BLS Public Data API. **21.9 million jobs were lost in two months**, unemployment peaked at 14.8%, and payrolls took 28 months to recover.

<sub>R · REST API · dplyr · ggplot2</sub>

</td>
</tr>
<tr>
<td width="50%" valign="top">

**🕸️ [Network structures in literature, social media and text](https://github.com/rolandkeszi/social-network-analysis)** · [**case study**](https://rolandkeszi.github.io/projects/network-analysis.html)

<a href="https://rolandkeszi.github.io/projects/network-analysis.html"><img src="https://raw.githubusercontent.com/rolandkeszi/social-network-analysis/main/figures/01_network_hubs.png" width="100%" alt="Facebook friendship network with three hubs highlighted"></a>

A **scale-free Facebook network** (4,039 users) with hubs 107, 1684 and 1912, a VOSviewer map of the sentiment analysis literature, and topical clusters in a tweet similarity network.

<sub>Python · NetworkX · Gephi · VOSviewer</sub>

</td>
<td width="50%" valign="top">

**📷 [Finding matching points between photos with SIFT](https://github.com/rolandkeszi/sift-feature-matching)** · [**case study**](https://rolandkeszi.github.io/projects/sift.html)

<a href="https://rolandkeszi.github.io/projects/sift.html"><img src="https://raw.githubusercontent.com/rolandkeszi/sift-feature-matching/main/figures/02_house_matches.png" width="100%" alt="SIFT matches between two photos of a house"></a>

Keypoint detection and matching on my own photos of two buildings. A textured house gives **about 1,250 reliable matches**; a repetitive facade gives far fewer. Brute-force and FLANN matching are compared, with Lowe's ratio test.

<sub>Python · OpenCV</sub>

</td>
</tr>
<tr>
<td colspan="2" align="center">

### 🗂️ [See all case studies →](https://rolandkeszi.github.io)

<sub>Question, data, method, results and limitations for every project on one page.</sub>

</td>
</tr>
</table>

| Project | What it does | Stack |
|---|---|---|
| 🤖 [**LLM vs. classical sentiment benchmark**](https://github.com/rolandkeszi/llm-sentiment-benchmark) | The 12-model comparison above. It covers prompt-based labelling through the OpenAI, Anthropic and Gemini APIs, BERT fine-tuning, CNN and LSTM networks on GloVe embeddings, and lexicon baselines. Each model gets confusion matrices and an error analysis. | Python, Hugging Face Transformers, Keras, scikit-learn |
| 💬 [**Sentiment analysis three ways**](https://github.com/rolandkeszi/nlp-sentiment-studies) | A word-embedding network on IMDb reviews (84.9%), a dense network vs an LSTM on five-class COVID-19 tweet sentiment (65.1% vs 68.5%), and the VADER lexicon on airline tweets (54.3%). [Case study](https://rolandkeszi.github.io/projects/sentiment-neural-networks.html). | Python, TensorFlow/Keras, NLTK, spaCy |
| ⚡ [**Power plant output estimation**](https://github.com/rolandkeszi/power-plant-output-prediction) | Regression models estimate a combined cycle plant's output from four ambient variables. Variable selection was done in SPSS, and the final linear model was validated on an independent sample. | Python, scikit-learn, TensorFlow, SPSS |
| 🏥 [**Hospital process mining**](https://github.com/rolandkeszi/hospital-process-mining) | Patient pathways, throughput times and staff workload reconstructed from a hospital event log, with three discovery algorithms compared. | Python, PM4Py, Graphviz |
| 🕸️ [**Network analysis**](https://github.com/rolandkeszi/social-network-analysis) | A scale-free Facebook network with its hubs, a map of the sentiment analysis literature, and a tweet similarity network. | Python, NetworkX, Gephi, VOSviewer |
| 📷 [**SIFT feature matching**](https://github.com/rolandkeszi/sift-feature-matching) | Keypoint detection and matching between photos of buildings, comparing brute-force and FLANN matching. | Python, OpenCV |
| ✈️ [**US airline tweets: sentiment dashboard**](https://github.com/rolandkeszi/USAir) | Interactive exploration by sentiment, airline and hour of day, with word clouds of what passengers write. | Streamlit, Plotly, pandas |
| 📈 [**COVID-19 labour-market shock (BLS API)**](https://github.com/rolandkeszi/bls-covid-labour-market) | An automated fetch → tidy → chart pipeline for official US labour statistics, with a reproducible CSV export. | R, REST API, ggplot2 |

---

### Toolbox

**Languages & data**<br>
<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"> <img alt="R" src="https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white"> <img alt="pandas" src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white"> <img alt="NumPy" src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white"> <img alt="SPSS" src="https://img.shields.io/badge/IBM%20SPSS-052FAD?style=flat-square&logo=ibm&logoColor=white">

**Machine learning & NLP**<br>
<img alt="scikit-learn" src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white"> <img alt="Hugging Face" src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black"> <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"> <img alt="Keras" src="https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white"> <img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white">

**LLM APIs**<br>
<img alt="Anthropic Claude" src="https://img.shields.io/badge/Claude%20API-191919?style=flat-square&logo=anthropic&logoColor=white"> <img alt="OpenAI" src="https://img.shields.io/badge/OpenAI%20API-412991?style=flat-square&logo=openai&logoColor=white"> <img alt="Google Gemini" src="https://img.shields.io/badge/Gemini%20API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white">

**Visualisation & apps**<br>
<img alt="Streamlit" src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white"> <img alt="Plotly" src="https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white"> <img alt="Matplotlib" src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square"> <img alt="SHAP" src="https://img.shields.io/badge/SHAP-explainable%20AI-8250df?style=flat-square"> <img alt="Jupyter" src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white"> <img alt="Google Colab" src="https://img.shields.io/badge/Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white">

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

További projektjeim: egy interaktív Streamlit-dashboard amerikai légitársaságokról szóló tweetek szentimentjéről, és egy R-ben írt elemzés, amely a BLS API adataiból mutatja be a COVID-19 munkaerőpiaci sokkját.

</details>

---

<p align="center">
  <sub>Open to research collaborations on LLM evaluation, text analytics and survey data. Reach me on <a href="https://www.linkedin.com/in/rolandkeszi/">LinkedIn</a>.</sub>
</p>
