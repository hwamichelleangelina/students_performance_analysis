# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding
Jelaskan latar belakang bisnis dari perushaan tersebut.

### Permasalahan Bisnis
Tuliskan seluruh permasalahan bisnis yang akan diselesaikan.

### Cakupan Proyek
Tuliskan cakupan proyek yang akan dikerjakan.

### Persiapan

Sumber data: ....

Setup environment:
```

```

## Business Dashboard
Jelaskan tentang business dashboard yang telah dibuat. Jika ada, sertakan juga link untuk mengakses dashboard tersebut.

## Menjalankan Sistem Machine Learning
Jelaskan cara menjalankan protoype sistem machine learning yang telah dibuat. Selain itu, sertakan juga link untuk mengakses prototype tersebut.

```

```

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
