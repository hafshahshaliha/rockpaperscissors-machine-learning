# Proyek Akhir: Menyelesaikan Permasalahan Turnover Karyawan pada Perusahaan Edutech  
> **Studi Kasus – PT Jayajaya (Platform Pembelajaran Daring)**

---

## 1. Business Understanding  
Perusahaan Edutech Jayajaya berkembang pesat namun mengalami **attrition ~14 %**, mengancam stabilitas tim serta efektivitas inisiatif strategis.

**Tujuan Proyek**  

1. Memprediksi karyawan yang berisiko resign.  
2. Mengidentifikasi faktor penyebab utama attrition.  
3. Menyajikan insight visual agar HR dapat intervensi tepat sasaran.

---

## 2. Permasalahan Bisnis  
| Masalah | Dampak | Pertanyaan |
|---------|--------|-----------|
| Attrition meningkat | Hilangnya talenta kritis & biaya rekrutmen tinggi | *Siapa* akan resign? |
| Insight terbatas | Intervensi HR reaktif | *Mengapa* mereka berisiko? |
| Tidak ada dashboard | Keputusan berbasis intuisi | Bagaimana menyajikan data? |

---

## 3. Cakupan Proyek  
- **Exploratory Data Analysis (EDA)** – statistik deskriptif & visual.  
- **Statistical Testing** – chi‑square (BusinessTravel, MaritalStatus, OverTime) & t‑test (Age, MonthlyIncome).  
- **Predictive Modelling** – One‑hot → Scaling → SMOTE → Random Forest (AUC 0.86).  
- **Feature Importance** – RF importance & SHAP.  
- **Deployment** – ekspor hasil prediksi & dashboard Tableau.

---

## 4. Dataset & Environment  

### 4.1 Dataset  
`employee_data_imputed.csv` – data historis karyawan (setelah proses imputasi).

### 4.2 Requirements  
File `requirements.txt`  


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
# Mac/Linux ➜ source venv/bin/activate
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
attrition_pipeline.pkl    # model terlatih
raw_input.csv             # data karyawan mentah (belum one‑hot)
predict.py                # skrip prediksi
```

### 6.2 Menjalankan Prediksi

```bash
python predict.py
```

Output ➜ **`attrition_prediction_result.xlsx`** berisi kolom:

\| EmployeeId | Attrition Probability | Predicted Class | Risk Level |

Hanya karyawan **Medium** & **High Risk** disertakan.

---

## 7. Business Dashboard

| Metode             | Cara Akses                                                                                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Tableau Public** | [https://public.tableau.com/app/profile/hafshah.shaliha/viz/HRAnalysisDashboard-2/Dashboard2](https://public.tableau.com/app/profile/hafshah.shaliha/viz/HRAnalysisDashboard-2/Dashboard2) |
| **File `.twbx`**   | Buka `hafshah_shaliha_uhvc-dashboard.twbx` di Tableau Desktop → Dashboard 2                                                                                                                         |

Dashboard menampilkan Prediction Table, Attrition Breakdown, Feature Importance, dsb.

---

## 8. Output Penting

| Berkas                                      | Fungsi                                                 |
| ------------------------------------------- | ------------------------------------------------------ |
| `attrition_prediction_result.xlsx`          | Daftar karyawan berisiko (probabilitas & level risiko) |
| `hafshah_shaliha_uhvc-dashboard.twbx` / Tableau link | Dashboard interaktif untuk manajemen                   |
| `HR_Attrition_Analysis.ipynb`               | Notebook EDA & modelling lengkap                       |

---

## 9. Kesimpulan & Rekomendasi

**Kesimpulan**

* Random Forest + SMOTE mencapai **akurasi 86 %**.
* Faktor utama: **OverTime**, **YearsWithCurrManager**, **EnvironmentSatisfaction**.
* Hanya 2 karyawan High Risk (prob ≥ 0.80) → intervensi retensi bisa sangat fokus.

**Rekomendasi**

1. **Compensation Review** untuk High Performers.
2. **Program Engagement & Lingkungan Kerja** (survei rutin, team‑bonding).
3. **Retention Check‑in** dengan manajer bagi 18 karyawan Medium Risk.

---

## 10. Author

* **Nama:** Hafshah Mar'atu Shaliha
* **Email:** [hafshahshalihaa@gmail.com](mailto:hafshahshalihaa@gmail.com)
* **Dicoding ID:** hafshah\_shaliha\_uhvc

Terima kasih telah menilai submission ini—silakan hubungi saya jika ada pertanyaan.

```

