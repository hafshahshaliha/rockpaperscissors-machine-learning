# Proyek Akhir Dicoding – Menyelesaikan Permasalahan Turnover Karyawan pada Perusahaan Edutech  
> **Studi Kasus:** PT Jayajaya (Platform Pembelajaran Daring)

---

## 1 | Business Understanding  

Perusahaan Edutech Jayajaya berkembang pesat dan bergantung pada talenta kunci di divisi penjualan, R&D, serta staf pendukung. Namun, **attrition ~14 %** mulai mengganggu stabilitas tim dan efektivitas inisiatif strategis.

### Tujuan  
1. **Memprediksi** karyawan berisiko resign.  
2. **Mengidentifikasi** faktor penyebab utama attrition.  
3. **Menyajikan** insight visual agar HR bisa melakukan intervensi tepat sasaran.

---

## 2 | Permasalahan Bisnis  

| Masalah | Dampak | Pertanyaan |
|---------|--------|-----------|
| Attrition meningkat | Hilangnya talenta kritis & biaya rekrutmen tinggi | *Siapa* akan resign? |
| Insight faktor resign terbatas | Intervensi HR reaktif | *Mengapa* mereka berisiko? |
| Belum ada dashboard | Pengambilan keputusan berbasis intuisi | Bagaimana menyajikan data secara ringkas? |

---

## 3 | Cakupan Proyek  

- **Exploratory Data Analysis (EDA)** – Statistik deskriptif & visual.  
- **Statistical Testing** – Chi‑square (BusinessTravel, MaritalStatus, OverTime) & t‑test (Age, MonthlyIncome).  
- **Predictive Modelling** – Pipeline: one‑hot → scaling → SMOTE → Random Forest (AUC 0.86).  
- **Feature Importance** – Visualisasi SHAP & RF importance.  
- **Deployment** – Hasil prediksi & importance diekspor, dashboard interaktif di Tableau.

---

## 4 | Persiapan  

### 4.1 Dataset  
`employee_data_imputed.csv` – data historis karyawan (setelah proses imputasi, lihat notebook **Model‑Based Imputation** pada folder *dependencies*).  

### 4.2 Environment Setup  

```bash
# 1) Buat virtual environment
python3 -m venv venv
source venv/bin/activate        # Windows → venv\Scripts\activate

# 2) Instal paket
pip install -r requirements.txt

---
