# 🩺 RiMedAI – Risk Medical Detection AI

## 📌 Deskripsi

RiMedAI adalah aplikasi web berbasis machine learning yang memprediksi risiko penyakit berdasarkan data pengguna. Model dilatih menggunakan data kesehatan pengguna dan diintegrasikan ke dalam antarmuka web menggunakan Streamlit, sehingga pengguna dapat langsung melakukan prediksi secara interaktif.


## 📁 Struktur Repositori

├── .streamlit <br>
│ └── config.toml <br>
├── deploy <br>
│ └── requirements.txt <br>
│ └── web-app.py <br>
├── export-model <br>
│ └── lr_jantung_smote.pkl <br>
│ └── Deteksi_diabetes_NN.pkl <br>
│ └── stroke_rf_bayes_model_smote.pkl <br>
├── image <br>
│ └── rimed-ai.png <br>
├── README.md <br>
├── notebook_inferensi_jantung.ipynb <br>
├── notebook_prediksi_diabetes.ipynb <br>
├── notebook_prediksi_jantung.ipynb <br>
└── notebook_prediksi_stroke.ipynb <br> 

**Keterangan:**
- Folder **.streamlit** berisi **config.toml** yang digunakan untuk melakukan konfigurasi antar muka web app (contohnya warna background).
- Folder **deploy** berisi web-app.py yang berisi kode untuk membangun antar muka web app RiMedAi beserta file requirements.txt untuk proses deployment di Streamlit Cloud. 
- Folder **export-model** berisi kumpulan file model hasil pelatihan machine learning untuk memprediksi risiko berbagai jenis penyakit. Setiap file merupakan model yang diekspor dari proses pelatihan yang dilakukan secara terpisah di notebook masing-masing sesuai dengan jenis penyakit yang diprediksi.
- Folder **image** berisi tangkapan layar aplikasi web RiMedAI.
- File **README.md** berisi dokumentasi repositori secara general.
- Setiap file **notebook .ipynb** berisi eksperimen pelatihan model machine learning untuk memprediksi risiko tiga jenis penyakit: stroke, penyakit jantung, dan diabetes. Setiap model dilatih secara terpisah dan terdokumentasi dalam notebook masing-masing sesuai dengan jenis penyakit yang diprediksi.

## 📊 Sumber Dataset
Berikut link sumber dataset yang digunakan untuk melatih masing-masing model prediksi risiko penyakit: 

**Stroke:** [Stroke Diagnosis and Health Metrics Data - Kaggle](https://www.kaggle.com/datasets/shriyashjagtap/stroke-diagnosis-and-health-metrics-data) <br>
**Jantung:** [Heart_Disease_Indicators - Kaggle](https://www.kaggle.com/datasets/bhaveshmisra/heart-disease-indicators/data) <br>
**Diabetes:** [Diabetes, Hypertension and Stroke Prediction - Kaggle](https://www.kaggle.com/datasets/prosperchuks/health-dataset?select=diabetes_data.csv)


## 🤖 Model Machine Learning
Model dilatih menggunakan algoritma klasifikasi baik itu dengan machine learning tradisional (dengan library Scikit Learn), maupun deep learning (dengan library Tensorflow). Proses pelatihan dan evaluasi dilakukan di dalam notebook .ipynb, di mana di dalamnya termasuk proses:

- Exploratory Data Analysis (EDA)
- Preprocessing (cleaning, encoding, scaling)
- Split data
- Training model
- Evaluasi performa
- Save model ke .pkl

Model yang telah dilatih disimpan dalam model.pkl dan digunakan di aplikasi web.

## 📈 Evaluasi Model Machine Learning


|               | Stroke       | Jantung                       | Diabetes       |
|---------------|--------------|-------------------------------|----------------|
| **Model**     | Bayes Search | Logistic Regression dan SMOTE | Neural Network |
| **Akurasi**   | 78,80%       | 75,20%                        | 75%            |
| **Precision** | 68,31%       | 56,28%                        | 73%            |
| **Recall**    | 51,78%       | 64,90%                        | 79%            |
| **F1-Score**  | 58,91%       | 60.57%                        | 76%            |


## 🖥️ Aplikasi Web (Streamlit)

Setup environment - Shell/Terminal untuk menjalankan deploy/web-app.py di lokal:

```
mkdir rimedai
cd rimedai
pipenv install
pipenv shell
pip install -r requirements.txt
```

Run web app di terminal lokal:
```
streamlit run web-app.py
```
Selain dijalankan di lokal, aplikasi web RiMedAI juga dapat diakses secara online melalui browser dengan link berikut: <br>
**https://rimed-ai.streamlit.app/**

<img src='https://raw.githubusercontent.com/RiMedAI/laskarai-capstone/refs/heads/main/image/rimed-ai.png'>

[**🎬Link Video Demo**](https://drive.google.com/file/d/1m_jrq05Wm9fm6i8Ac9C-SGyptW0gtf_6/view?usp=drive_link)
