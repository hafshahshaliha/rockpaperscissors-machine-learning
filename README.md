# Proyek Akhir: Menyelesaikan Permasalahan Turnover Karyawan pada Perusahaan Edutech  
> **Studi Kasus – PT Jayajaya**

---

## 1. Business Understanding  
Perusahaan Edutech Jayajaya berkembang pesat tetapi mengalami **attrition ~14 %**, mengancam stabilitas tim serta efektivitas inisiatif strategis.

**Tujuan Proyek**  
1. Memprediksi karyawan berisiko resign.  
2. Mengidentifikasi faktor penyebab utama.  
3. Menyajikan insight visual agar HR dapat intervensi tepat sasaran.

---

## 2. Permasalahan Bisnis  
| Masalah | Dampak | Pertanyaan |
|---------|--------|-----------|
| Attrition meningkat | Hilangnya talenta kritis & biaya rekrutmen tinggi | *Siapa* akan resign? |
| Insight terbatas | Intervensi HR reaktif | *Mengapa* mereka berisiko? |
| Tidak ada dashboard | Keputusan berbasis intuisi | Bagaimana menyajikan data? |

---

## 3. Cakupan Proyek  
- **EDA & Statistik** – distribusi demografi, lembur, kepuasan kerja.  
- **Statistical Testing** – chi‑square & t‑test variabel kunci.  
- **Predictive Modelling** – One‑hot → Scaling → SMOTE → Random Forest (AUC 0.86).  
- **Feature Importance** – RF importance & SHAP.  
- **Deployment** – hasil prediksi → Excel, dashboard Tableau.

---

## 4. Dataset & Environment  

### 4.1 Dataset  
`employee_data_imputed.csv` – data historis karyawan (setelah imputasi).

### 4.2 Requirements  
```

numpy==1.24.0
pandas==1.5.3
scipy==1.9.3
scikit-learn==1.1.3
imbalanced-learn==0.10.1
matplotlib==3.6.3
seaborn==0.11.2
xgboost==1.4.2

````

### 4.3 Setup Environment  
```bash
python -m venv venv
# Windows ➜ venv\Scripts\activate
# macOS/Linux ➜ source venv/bin/activate
pip install -r requirements.txt
````

---

## 5. Menjalankan Exploratory Data Analysis

```bash
jupyter notebook HR_Attrition_Analysis.ipynb
```

Notebook memuat EDA, preprocessing, training, evaluasi, serta ekspor `attrition_pipeline.pkl`.

---

## 6. Prediksi Risiko Attrition (`predict.py`)

### 6.1 Penempatan Berkas

```
model/
├─ attrition_pipeline.pkl
├─ raw_input.csv
predict.py
```

> Jika input bernama `no_attrition.csv`, ubah variabel `INPUT_CSV` di `predict.py`.

### 6.2 Menjalankan Prediksi

```bash
python predict.py
```

Output ➜ **`attrition_prediction_result.xlsx`** (karyawan Medium & High Risk).

---

## 7. Business Dashboard

| Metode             | Cara Akses                                                                                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Tableau Public** | [https://public.tableau.com/app/profile/hafshah.shaliha/viz/HRAnalysisDashboard-2/Dashboard2](https://public.tableau.com/app/profile/hafshah.shaliha/viz/HRAnalysisDashboard-2/Dashboard2) |
| **File `.twbx`**   | Buka `HRAnalysisDashboard-2.twbx` di Tableau Desktop → Dashboard 2                                                                                                                         |

---

## 8. Berkas yang Tertera

```
submission/
├─ preprocessing/
│  ├─ Model-Based Imputation.ipynb
│  └─ employee_data_imputed.csv
│
├─ model/
│  ├─ attrition_pipeline.pkl
│  └─ raw_input.csv
│
├─ HR_Attrition_Analysis.ipynb
├─ HRAnalysisDashboard-2.twbx
├─ predict.py
├─ attrition_prediction_result.xlsx   # (terbentuk setelah menjalankan predict.py)
├─ requirements.txt
└─ README.md
```

> **Keterangan:**
> • Folder **preprocessing/** memuat notebook imputasi & dataset bersih.
> • Folder **model/** memuat pipeline terlatih dan data input untuk inferensi.
> • `predict.py` akan mengambil `model/attrition_pipeline.pkl` & `model/raw_input.csv` lalu menulis hasil ke `attrition_prediction_result.xlsx`.

---

## 9. Kesimpulan & Rekomendasi

**Kesimpulan**

* Random Forest + SMOTE mencapai **akurasi 86 %**.
* Faktor utama: **OverTime**, **YearsWithCurrManager**, **EnvironmentSatisfaction**.
* Hanya 2 karyawan High Risk (prob ≥ 0.80) → intervensi retensi dapat difokuskan.

**Rekomendasi**

1. Compensation Review bagi High Performers.
2. Program Engagement & Lingkungan Kerja (survei rutin, team‑bonding).
3. Retention Check‑in untuk 18 karyawan Medium Risk.

---

## 10. Author

* **Nama:** Hafshah Mar'atu Shaliha
* **Email:** [hafshahshalihaa@gmail.com](mailto:hafshahshalihaa@gmail.com)
* **Dicoding ID:** hafshah\_shaliha\_uhvc

Terima kasih telah menilai submission ini—hubungi saya jika ada pertanyaan lebih lanjut.


