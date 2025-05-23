# Proyek Akhir: Menyelesaikan Permasalahan Institusi Pendidikan

## Business Understanding
Jaya Jaya Institut adalah institusi pendidikan tinggi yang telah berdiri sejak tahun 2000 dan telah mencetak banyak lulusan berkualitas. Namun, institusi ini menghadapi tantangan serius: tingginya angka mahasiswa yang tidak menyelesaikan pendidikan alias dropout.

Masalah ini tidak hanya berdampak pada reputasi institusi, tetapi juga pada efisiensi operasional dan keberhasilan mahasiswa secara individu. Untuk itu, Jaya Jaya Institut ingin mendeteksi sedini mungkin siswa yang berisiko dropout agar dapat diberikan intervensi dan bimbingan khusus.

### Permasalahan Bisnis
- Bagaimana memprediksi apakah seorang mahasiswa akan berhasil melanjutkan studinya atau tidak?
- Apa saja faktor yang memengaruhi mahasiswa untuk drop out dari Jaya Jaya Institut?
- Bagaimana menyajikan prediksi ini dalam bentuk sistem yang mudah digunakan oleh pihak kampus?

### Cakupan Proyek
- Eksplorasi dan pemrosesan dataset mahasiswa untuk menentukan feature importance terhadap status mahasiswa.
- Feature engineering untuk membuat atribut turunan yang mendukung prediksi.
  * **Pass Rate Features**:
  
    * `pass_rate_1st`: Rasio mata kuliah semester 1 yang lulus terhadap jumlah yang diambil.
    * `pass_rate_2nd`: Rasio mata kuliah semester 2 yang lulus terhadap jumlah yang diambil.
    * `pass_rate_total`: Rasio total mata kuliah yang lulus (semester 1 + 2) terhadap total yang diambil.
  
  * **Missing Evaluation Features**:
  
    * `missing_eval_1st`: Proporsi mata kuliah semester 1 tanpa evaluasi terhadap jumlah yang diambil.
    * `missing_eval_2nd`: Proporsi mata kuliah semester 2 tanpa evaluasi terhadap jumlah yang diambil.
    * `missing_eval_total`: Proporsi total mata kuliah tanpa evaluasi (semester 1 + 2) terhadap total yang diambil.
  
  * **Grade Features**:
  
    * `avg_grade`: Rata-rata nilai dari semester 1 dan semester 2.
    * `grade_gap`: Selisih antara nilai rata-rata masuk (admission grade) dan nilai akademik saat ini.
  
  * **Academic Stats Features**:
  
    * `total_enrolled`: Total mata kuliah yang diambil di kedua semester.
    * `total_approved`: Total mata kuliah yang lulus di kedua semester.
    * `total_evaluations`: Total evaluasi yang dilakukan di kedua semester.
    * `total_failed`: Jumlah mata kuliah yang tidak lulus.
    * `unit_completion_ratio`: Rasio kelulusan mata kuliah terhadap jumlah yang diambil.
  
  * **Financial & Special Case Risk Features**:
  
    * `financial_risk`: Indikator risiko keuangan mahasiswa berdasarkan status pembayaran, utang, dan beasiswa.
    * `special_case`: Indikator status khusus.
- Pelatihan dan evaluasi beberapa model machine learning (Random Forest, XGBoost, Deep Learning).
- Ensemble modeling untuk meningkatkan akurasi prediksi.
- Pembuatan model Machine Learning dengan Python untuk menampilkan hasil prediksi.
- Pembuatan prototipe aplikasi dengan Streamlit.
- Pengembangan dashboard visualisasi data.

### Persiapan

Sumber data: [students' performance](https://github.com/dicodingacademy/dicoding_dataset/blob/main/students_performance/data.csv)

Setup environment:
Pastikan environment Python telah dilengkapi dengan library berikut:
```
pip install requirements.txt
```
```
├─── `app.py` – Aplikasi untuk Streamlit
├─── `notebook.ipynb` – Notebook eksplorasi dan model training
├─── `requirements.txt` – Requirements untuk kebutuhan library
├─── model
  ├─── `xgb_model.pkl` – Model XGBoost
  ├─── `rf_model_compressed.pkl` – Model Random Forest
  ├─── `dl_model.h5` – Model Deep Learning (Keras)
  ├─── `meta_model.pkl` – Model Ensemble
  ├─── `scaler.pkl` – Objek StandardScaler
  ├─── `scaler_columns.pkl` – Objek StandardScaler dalam Bentuk Kolom
  └─── `label_encoders.pkl` – Encoder label
└─── data.csv – Dataset
```

## Business Dashboard
Dashboard yang dibuat bertujuan untuk memvisualisasikan dan memantau faktor-faktor penyebab utama dari status mahasiswa secara interaktif. Visualisasi ini mencakup:
- Distribusi dan perbandingan status mahasiswa berdasarkan fitur penting seperti pembayaran biaya kuliah, nilai mahasiswa, dll.
- Pemantauan demografi mahasiswa.
- Insight berdasarkan segmentasi kelompok mahasiswa.
- Business Dashboard: [Jaya Jaya Institute Students' Performance Analysis Dashboard](https://lookerstudio.google.com/reporting/275ca653-22b8-4fde-a66d-e35619cd6f57)

## Menjalankan Sistem Machine Learning
Untuk menjalankan sistem prediksi:

1. Pastikan semua file model (`.pkl` dan `.h5`) berada di direktori yang sama. Pastikan juga streamlit telah terinstal.
```
pip install streamlit
```
2. Jalankan `app.py`:

```
python app.py
```

3. Ikuti prompt untuk mengisi data mahasiswa.
4. Sistem akan memproses input dan menampilkan hasil prediksi status mahasiswa.

Contoh output:

```
Prediksi Status Mahasiswa: Graduate
```
Deployment dapat diakses pada Streamlit Cloud berikut: [https://jaya-jaya-students-status.streamlit.app/](https://jaya-jaya-students-status.streamlit.app/)

## Conclusion
- Mahasiswa dengan banyak mata kuliah yang **tidak lulus** cenderung dropout.  
  - Informasi terkait: `Curricular_units_1st_sem_enrolled`, `Curricular_units_2nd_sem_enrolled`, `Curricular_units_1st_sem_approved`, `Curricular_units_2nd_sem_approved`

- Rasio kelulusan yang **rendah dibanding jumlah mata kuliah yang diambil** sangat berpengaruh terhadap dropout.  
  - Informasi terkait: `Curricular_units_1st_sem_enrolled`, `Curricular_units_2nd_sem_enrolled`, `Curricular_units_1st_sem_approved`, `Curricular_units_2nd_sem_approved`

- Jumlah mata kuliah yang **lulus di semester 2** menjadi indikator penting kelanjutan studi.  
  - Informasi terkait: `Curricular_units_2nd_sem_approved`

- Mahasiswa yang **menunggak pembayaran biaya kuliah** berisiko lebih tinggi untuk keluar.  
  - Informasi terkait: `Tuition_fees_up_to_date`

- Nilai semester yang **rendah** menjadi salah satu pemicu kurangnya motivasi studi.  
  - Informasi terkait: `Curricular_units_1st_sem_grade`, `Curricular_units_2nd_sem_grade`

### Rekomendasi Action Items
Berikan beberapa rekomendasi action items yang harus dilakukan perusahaan guna menyelesaikan permasalahan atau mencapai target mereka.
1. Pantau dan Intervensi Mahasiswa dengan Rasio Kelulusan Rendah
  - **Feature terkait:** `Curricular_units_1st_sem_approved`, `Curricular_units_2nd_sem_approved`, `Curricular_units_1st_sem_enrolled`, `Curricular_units_2nd_sem_enrolled`
  - Mahasiswa dengan jumlah mata kuliah yang diambil banyak, tetapi yang lulus sedikit, memiliki **unit_completion_ratio** rendah dan **total_failed** tinggi.
  - **Tindakan:** Buat sistem peringatan dini (early warning system) untuk mengidentifikasi mahasiswa dengan rasio kelulusan < 50% dan tawarkan program mentoring atau remedial.

2. Evaluasi Kinerja Akademik Berdasarkan Nilai Rata-rata Semester
  - **Feature terkait:** `Curricular_units_1st_sem_grade`, `Curricular_units_2nd_sem_grade`
  - Nilai akademik yang rendah (low `avg_grade`) dapat menjadi indikator motivasi atau kesiapan yang rendah.
  - **Tindakan:** Sediakan sesi konseling akademik atau workshop peningkatan belajar bagi mahasiswa dengan nilai rata-rata < 10.

3. Fokus pada Semester Awal: Penilaian Rasio Kelulusan per Semester
  - **Feature terkait:** `Curricular_units_1st_sem_approved`, `Curricular_units_1st_sem_enrolled`, `Curricular_units_2nd_sem_approved`, `Curricular_units_2nd_sem_enrolled`
  - Rasio kelulusan per semester (`pass_rate_total`) yang rendah menjadi indikator utama risiko dropout.
  - **Tindakan:** Analisis performa per semester untuk mendesain intervensi yang lebih cepat sebelum semester kedua.

4. Perhatikan Mahasiswa dengan Tunggakan Pembayaran
  - **Feature terkait:** `Tuition_fees_up_to_date`
  - Mahasiswa yang belum membayar biaya kuliah tepat waktu menunjukkan risiko finansial yang bisa berdampak pada dropout.
  - **Tindakan:** Sediakan opsi cicilan, bantuan keuangan, atau pengingat berkala agar mahasiswa tetap bisa melanjutkan studi.

5. Buat Laporan Rutin Tentang Rasio Gagal Mahasiswa
  - **Feature terkait:** `Curricular_units_1st_sem_approved`, `Curricular_units_2nd_sem_approved`, `Curricular_units_1st_sem_enrolled`, `Curricular_units_2nd_sem_enrolled`
  - Jumlah `total_failed` yang tinggi menunjukkan ketidaksesuaian beban studi dengan kemampuan mahasiswa.
  - **Tindakan:** Evaluasi kurikulum atau proses pemilihan mata kuliah agar lebih adaptif terhadap kemampuan mahasiswa baru. Dari evaluasi ini, institut dapat bertindak lebih cepat untuk memberikan bimbingan khusus.
