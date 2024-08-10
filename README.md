# **Implementasi AHP dalam Pengambilan Keputusan Prioritas Pasien ICU**
---

**Objective**
Rumah sakit dengan skala besar bertujuan untuk mengoptimalkan manajemen distribusi ruang ICU. Mereka mengalami kesulitan dalam memprioritaskan pasien yang memerlukan kamar ICU, dengan mempertimbangkan beragam aspek medis dan administratif. Fokus utama mereka adalah memastikan pasien dengan kebutuhan perawatan intensif paling mendesak mendapat prioritas tertinggi, meningkatkan mutu layanan kesehatan, meminimalkan masa tunggu, serta memaksimalkan pemanfaatan fasilitas rumah sakit.

 - Dataset: [Healthcare Dataset](https://www.kaggle.com/datasets/prasad22/healthcare-dataset?resource=download) , merupakan dataset publik yang mencakup informasi tentang pasien seperti nama, usia, jenis kelamin, kondisi medis, tanggal masuk, dokter, rumah sakit, penyedia asuransi, jumlah tagihan, nomor kamar, jenis penerimaan, tanggal keluar, obat-obatan, dan hasil tes dan diambil dari platform **Kaggle**.

---
Dibuat oleh : **David Mario**

GitHub : [DavidMarioYS](https://github.com/DavidMarioYS)

Email : davidmario484@gmail.com
---

### **1. Pendahuluan**
   - **Tujuan**: Menggunakan metode **Analytic Hierarchy Process (AHP)** untuk menentukan prioritas pasien ICU berdasarkan beberapa kriteria penting. 
   - **Konsep AHP**: AHP adalah metode yang memecah masalah keputusan kompleks menjadi hierarki yang lebih sederhana, memungkinkan penilaian kualitatif dan kuantitatif dari setiap kriteria dan sub-kriteria.

### **2. Pengolahan Data dan Implementasi AHP**
   - **Definisi Kriteria dan Sub-Kriteria**:
     - Data yang digunakan dipecah ke dalam beberapa kriteria seperti `Gender`, `Admission Type`, `Medical Condition`, `Age`, dan `Billing Amount`.
     - Masing-masing kriteria memiliki bobot tersendiri yang mencerminkan kepentingannya relatif terhadap kriteria lain.
   
   - **Inisialisasi Model `ICUPriorityModel`**:
     - Sebuah kelas Python dibuat untuk mengkapsulasi logika perhitungan skor prioritas ICU. 
     - Bobot untuk kriteria dan sub-kriteria ditentukan sebelumnya menggunakan hasil dari metode AHP.
   
   - **Perhitungan Skor Prioritas**:
     - Untuk setiap pasien, skor untuk masing-masing kriteria dihitung dengan mengalikan nilai bobot kriteria dengan nilai bobot sub-kriteria yang relevan.
     - Hasil perhitungan ini digabungkan untuk memberikan skor prioritas total (`ICU Priority Score`).
   
   - **Pengkategorian Prioritas**:
     - Pasien kemudian dikategorikan ke dalam tiga kelompok: `Sangat Prioritas`, `Prioritas`, dan `Tidak Prioritas`. Kategori ini didasarkan pada nilai kuartil dari distribusi skor prioritas.
   
   - **Implementasi dalam Interaktif**:
     - Notebook juga mengimplementasikan interaksi pengguna dengan widgets untuk menghitung skor prioritas ICU berdasarkan input manual dari kriteria yang relevan.

### **3. Visualisasi dan Interpretasi**
   - **Treemap**: 
     - Visualisasi ini digunakan untuk menampilkan distribusi bobot kriteria dan sub-kriteria dalam model, membantu pengguna memahami pengaruh relatif dari masing-masing kriteria.
   
   - **Histogram Skor Prioritas**:
     - Menampilkan distribusi dari skor prioritas ICU yang dihitung, memberikan wawasan tentang bagaimana pasien dikelompokkan berdasarkan prioritasnya.
   
   - **Bar Chart Kategori Prioritas**:
     - Memvisualisasikan jumlah pasien dalam setiap kategori prioritas, membantu memahami proporsi pasien dalam setiap kategori.

### **4. Hasil yang Didapat**
   - **Penggunaan AHP untuk Prioritas ICU**:
     - Hasil menunjukkan bahwa AHP efektif dalam menentukan prioritas pasien berdasarkan kondisi medis dan faktor lainnya.
     - Pasien dengan skor tertinggi diprioritaskan untuk mendapatkan perawatan ICU lebih dahulu.
   
   - **Pengkategorian Efektif**:
     - Pengkategorian membantu manajemen rumah sakit dalam membuat keputusan cepat, memastikan pasien yang paling membutuhkan mendapatkan penanganan sesuai.

### **5. Penerapan dalam Pengambilan Keputusan Nyata**
   - **Transparansi dan Akurasi**:
     - Proyek ini memperlihatkan bagaimana AHP bisa diterapkan dalam skenario nyata untuk mendukung keputusan yang berdampak besar pada keselamatan pasien.
   
   - **Alokasi Sumber Daya**:
     - Model ini membantu mengalokasikan sumber daya ICU secara lebih efisien dan efektif, berdasarkan prioritas medis yang telah dihitung.

### **6. Keterpaduan dan Implementasi Teknologi**
   - **Penggunaan Python dan Library Pendukung**:
     - Seluruh tahapan proyek, mulai dari pemrosesan data hingga pengembangan model dan visualisasi, didukung oleh Python dan library seperti Pandas dan Plotly.
     - Teknologi ini memastikan bahwa proyek dapat direplikasi dan dikembangkan lebih lanjut.

### **Kesimpulan**
Secara keseluruhan, proyek ini berhasil mencapai tujuannya dalam menyediakan alat bantu pengambilan keputusan yang efektif dan efisien untuk menentukan prioritas pasien ICU. Dengan alur perhitungan yang jelas dan pengkategorian prioritas yang membantu, proyek ini memberikan hasil yang signifikan dan relevan untuk pengambilan keputusan yang cepat dan tepat di lingkungan rumah sakit.