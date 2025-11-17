# Tugas-python

# 📊 *LAPORAN PRAKTIKUM ANALISIS DATA & VISUALISASI DATA*

## *Identitas*
- *Mata Pelajaran:* Koding Kecerdasan Artifisial
- *Kelas:* XI RPL 3
- *Nama:* [Dean gavrilla Azora Pribadi]
- *Tanggal:* [17-11-2025]

---

## *🎯 Tujuan Pembelajaran*
1. Siswa mampu menghitung ukuran statistik dasar menggunakan Pandas
2. Siswa mampu menganalisis pola data berdasarkan rata-rata dan persebaran
3. Siswa mampu membuat visualisasi data sederhana menggunakan matplotlib python

---

## *🛠️ Tools & Library yang Digunakan*
- Python 3.13
- Pandas
- Matplotlib
- Seaborn
- VS Code

---

## *📝 Langkah Instalasi*

bash
pip install pandas
pip install matplotlib
pip install seaborn


---

## *💻 Kode Program*

python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Membaca dataset
data = pd.read_csv('nilai_siswa.csv')

# Tampilkan Informasi Data
print("=== INFORMASI DATA ===")
data.info()
print("\n")

# Tampilkan 5 data pertama
print("=== 5 BARIS PERTAMA ===")
print(data.head())
print("\n")

# Tampilkan statistik deskriptif
print("=== STATISTIK DESKRIPTIF ===")
print(data.describe())
print("\n")

# Hitung rata-rata, median, dan modus
print("=== UKURAN STATISTIK ===")
print("Rata-rata:", data['Nilai'].mean())
print("Median:", data['Nilai'].median())
print("Modus:", data['Nilai'].mode()[0])
print("\n")

# Tampilkan nilai per mata pelajaran - Matematika
print("=== NILAI MATEMATIKA ===")
matematika = data[data['Matpel'] == 'Matematika']
print(matematika)
print("\n")

# Bahasa Inggris
print("=== NILAI BAHASA INGGRIS ===")
bahasa_inggris = data[data['Matpel'] == 'Bahasa Inggris']
print(bahasa_inggris)
print("\n")

# Bahasa Indonesia
print("=== NILAI BAHASA INDONESIA ===")
bahasa_indonesia = data[data['Matpel'] == 'Bahasa Indonesia']
print(bahasa_indonesia)
print("\n")

# Produktif
print("=== NILAI PRODUKTIF ===")
produktif = data[data['Matpel'] == 'Produktif']
print(produktif)
print("\n")

# Tampilkan nilai maksimum dan minimum per mata pelajaran
print("=== NILAI MAKSIMUM DAN MINIMUM PER MATA PELAJARAN ===")
print(data.groupby('Matpel')['Nilai'].agg(['max', 'min']))
print("\n")

# Buat grafik batang rata-rata nilai per mapel
print("Membuat diagram batang...")
rata = data.groupby('Matpel')['Nilai'].mean()
rata.plot(kind='bar')
plt.title('Rata-Rata Nilai per Mata Pelajaran')
plt.xlabel('Mata Pelajaran')
plt.ylabel('Nilai Rata-Rata')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# Buat diagram boxplot
print("Membuat boxplot...")
sns.boxplot(x='Matpel', y='Nilai', data=data)
plt.title('Sebaran Nilai per Mata Pelajaran')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

print("\n=== ANALISIS SELESAI ===")


---

## *📊 Output Program*

### *1. Informasi Data*

=== INFORMASI DATA ===
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 22 entries, 0 to 21
Data columns (total 3 columns):
 #   Column  Non-Null Count  Dtype 
---  ------  --------------  ----- 
 0   Nama    22 non-null     object
 1   Matpel  22 non-null     object
 2   Nilai   22 non-null     int64
dtypes: int64(1), object(2)
memory usage: 660.0+ bytes


### *2. Lima Baris Pertama*

=== 5 BARIS PERTAMA ===
     Nama            Matpel  Nilai
0     Ade  Bahasa Indonesia     87
1    Aira  Bahasa Indonesia     88
2    Badi    Bahasa Inggris     78
3    Cyla    Bahasa Inggris     90
4  Khansa        Matematika     98


### *3. Statistik Deskriptif*

=== STATISTIK DESKRIPTIF ===
           Nilai
count  22.000000
mean   86.318182
std     6.066193
min    75.000000
25%    85.000000
50%    86.500000
75%    90.000000
max    98.000000


### *4. Ukuran Statistik*

=== UKURAN STATISTIK ===
Rata-rata: 86.31818181818181
Median: 86.5
Modus: 85


### *5. Nilai Maksimum dan Minimum per Mata Pelajaran*

=== NILAI MAKSIMUM DAN MINIMUM PER MATA PELAJARAN ===
                  max  min
Matpel                    
Bahasa Indonesia   88   87
Bahasa Inggris     90   78
Matematika         98   85
Produktif          90   75


### *6. Visualisasi Data*

*Diagram Batang - Rata-Rata Nilai per Mata Pelajaran:*

![Bar Chart](screenshot_bar_chart.png)
Keterangan: Grafik menunjukkan rata-rata nilai setiap mata pelajaran

*Boxplot - Sebaran Nilai per Mata Pelajaran:*

![Boxplot](screenshot_boxplot.png)
Keterangan: Boxplot menunjukkan distribusi, median, dan outlier nilai per mata pelajaran

---

## *📈 Analisis dan Pertanyaan*

### *1. Mapel mana yang memiliki rata-rata nilai tertinggi?*

*Jawaban:* Mata pelajaran *Matematika* memiliki rata-rata nilai tertinggi yaitu sekitar *91.5*. Hal ini menunjukkan bahwa siswa memiliki pemahaman yang sangat baik dalam mata pelajaran Matematika dan kemampuan numerik mereka cukup kuat.

---

### *2. Mapel mana yang memiliki nilai terendah?*

*Jawaban:* Mata pelajaran *Produktif* memiliki nilai terendah yaitu *75*. Ini mengindikasikan bahwa ada siswa yang mengalami kesulitan dalam mata pelajaran Produktif dan memerlukan bimbingan tambahan untuk meningkatkan pemahamannya.

---

### *3. Bagaimana visualisasi membantu dalam memahami data?*

*Jawaban:* Visualisasi sangat membantu dalam memahami data karena:

- *Diagram Batang (Bar Chart)* memudahkan perbandingan rata-rata nilai antar mata pelajaran secara visual dalam sekali pandang. Kita dapat langsung mengidentifikasi mata pelajaran mana yang memiliki performa terbaik dan mana yang perlu peningkatan.

- *Boxplot* memberikan informasi yang sangat komprehensif tentang:
  - Median (garis tengah dalam kotak)
  - Kuartil atas dan bawah (batas kotak)
  - Rentang nilai (whisker)
  - Outlier atau nilai ekstrem (titik di luar whisker)
  - Konsistensi nilai siswa per mata pelajaran

- *Efisiensi Pemahaman*: Grafik lebih mudah dan cepat dipahami dibandingkan membaca tabel angka. Otak manusia lebih mudah memproses informasi visual.

- *Identifikasi Pola*: Melalui visualisasi, kita dapat dengan mudah melihat pola, tren, dan anomali dalam data yang mungkin terlewatkan jika hanya melihat angka-angka.

- *Komunikasi Data*: Visualisasi memudahkan dalam menyampaikan insight kepada orang lain, seperti guru, kepala sekolah, atau orang tua siswa.

---

## *🤔 Refleksi Siswa*

### *1. Apa hal baru yang kamu pelajari dari kegiatan analisis dan visualisasi data?*

*Jawaban:* Hal baru yang saya pelajari dari kegiatan ini adalah:

- *Penggunaan Library Python untuk Data Science*: Saya belajar menggunakan Pandas untuk manipulasi data, Matplotlib untuk membuat grafik, dan Seaborn untuk visualisasi statistik yang lebih advanced.

- *Statistik Deskriptif*: Saya memahami pentingnya ukuran statistik seperti mean (rata-rata), median (nilai tengah), modus (nilai paling sering muncul), serta standar deviasi untuk memahami karakteristik data.

- *Grouping dan Aggregation*: Saya belajar cara mengelompokkan data berdasarkan kategori tertentu (groupby) dan melakukan agregasi seperti mencari nilai maksimum, minimum, dan rata-rata per kelompok.

- *Interpretasi Visualisasi*: Saya dapat membaca dan menginterpretasikan boxplot, termasuk memahami apa itu outlier, kuartil, dan sebaran data.

- *Data-Driven Decision Making*: Saya menyadari bahwa dengan data dan analisis yang tepat, kita dapat membuat keputusan yang lebih objektif dan berbasis bukti, misalnya menentukan mata pelajaran mana yang memerlukan perhatian khusus.

- *Workflow Analisis Data*: Dari membaca data, eksplorasi, analisis statistik, hingga visualisasi - saya memahami alur kerja lengkap seorang data analyst.

---

### *2. Kesulitan apa yang kamu alami dalam membuat grafik?*

*Jawaban:* Kesulitan yang saya alami dalam membuat grafik antara lain:

- *Error KeyError*: Awalnya saya mengalami error karena salah menulis nama kolom. Saya menulis 'Mapel' padahal di dataset sebenarnya bernama 'Matpel'. Ini mengajarkan saya pentingnya teliti dalam penulisan kode.

- *Sintaks Import yang Salah*: Sempat bingung dengan sintaks import yang benar. Awalnya menggunakan __pandas__ yang ternyata salah, seharusnya hanya pandas.

- *Mengatur Rotasi Label*: Label pada sumbu x tumpang tindih karena nama mata pelajaran yang panjang. Saya harus belajar menggunakan parameter rotation=45 dan tight_layout() untuk mengatasinya.

- *Memahami Parameter Fungsi*: Banyak parameter dalam fungsi plotting seperti kind, x, y, data yang awalnya membingungkan. Saya harus membaca dokumentasi dan mencoba beberapa kali.

- *Menampilkan Grafik*: Awalnya grafik tidak muncul karena lupa menambahkan plt.show().

- *Menyimpan Grafik*: Saya juga belajar cara menyimpan grafik sebagai file gambar menggunakan plt.savefig() untuk dokumentasi.

Namun, setelah mencoba berkali-kali, membaca error message dengan teliti, dan mencari solusi di dokumentasi atau Stack Overflow, saya mulai memahami dan terbiasa dengan proses pembuatan visualisasi data.

---

### *3. Menurut kamu AI apa membantu dalam analisis sebuah data?*

*Jawaban:* Ya, AI sangat membantu dalam analisis data. Berikut adalah berbagai cara AI berkontribusi:

*1. Kecepatan dan Efisiensi:*
- AI dapat memproses jutaan baris data dalam hitungan detik, sesuatu yang mustahil dilakukan manual oleh manusia.
- Otomatisasi tugas-tugas berulang seperti data cleaning, preprocessing, dan transformasi.

*2. Akurasi dan Konsistensi:*
- Mengurangi human error dalam perhitungan statistik dan analisis
- Memberikan hasil yang konsisten setiap kali dijalankan dengan data yang sama

*3. Pattern Recognition (Pengenalan Pola):*
- AI dapat menemukan pola tersembunyi dalam data yang sulit atau bahkan tidak mungkin ditemukan oleh manusia
- Machine Learning dapat mengidentifikasi korelasi dan hubungan kompleks antar variabel

*4. Prediksi dan Forecasting:*
- Algoritma AI dapat memprediksi tren masa depan berdasarkan data historis
- Contoh: memprediksi nilai siswa di semester depan, atau memprediksi siswa yang berisiko tidak lulus

*5. Visualisasi Otomatis:*
- AI dapat merekomendasikan jenis visualisasi terbaik untuk tipe data tertentu
- Tools modern bahkan dapat membuat dashboard interaktif secara otomatis

*6. Natural Language Processing (NLP):*
- AI dapat menganalisis data teks seperti feedback siswa atau komentar
- Sentiment analysis untuk memahami persepsi dan perasaan

*7. Personalisasi dan Rekomendasi:*
- Dalam konteks pendidikan, AI dapat memberikan rekomendasi pembelajaran yang dipersonalisasi untuk setiap siswa berdasarkan analisis performa mereka

*8. Anomaly Detection:*
- AI dapat mendeteksi outlier atau nilai yang tidak normal secara otomatis
- Penting untuk quality control dan fraud detection

*Contoh Konkret dalam Praktikum Ini:*
- Library Pandas menggunakan algoritma optimized untuk operasi data yang cepat
- Matplotlib dan Seaborn memiliki algoritma untuk menghasilkan visualisasi yang informatif
- Fungsi describe(), mean(), median() menggunakan komputasi efisien
- Groupby operations menggunakan algoritma yang dioptimalkan untuk performa

*Kesimpulan:*
AI bukan hanya membantu, tetapi sudah menjadi *kebutuhan esensial* dalam analisis data modern. Dalam era big data, kemampuan AI untuk memproses, menganalisis, dan mengekstrak insight dari data menjadi sangat vital untuk pengambilan keputusan yang cerdas dan berbasis bukti, baik dalam dunia pendidikan, bisnis, kesehatan, maupun berbagai bidang lainnya.

---

## *📁 Struktur Proyek*


PYTHON/
└── Analysis/
    ├── analisis.py
    ├── nilai_siswa.csv
    ├── screenshot_bar_chart.png
    ├── screenshot_boxplot.png
    └── README.md


---

## *🎓 Kesimpulan*

Praktikum ini berhasil menunjukkan bagaimana Python dengan library Pandas, Matplotlib, dan Seaborn dapat digunakan untuk:
1. ✅ Melakukan analisis statistik deskriptif
2. ✅ Mengidentifikasi pola dalam data nilai siswa
3. ✅ Membuat visualisasi yang informatif dan mudah dipahami
4. ✅ Mengambil insight untuk perbaikan pembelajaran

Data menunjukkan bahwa siswa secara umum memiliki performa yang baik (rata-rata 86.32), namun ada ruang untuk perbaikan terutama pada mata pelajaran Produktif yang memiliki nilai terendah.

---

## *📸 Screenshot*

Sisipkan screenshot di sini:
- Screenshot grafik bar chart
- Screenshot grafik boxplot

---

## *👨‍💻 Dibuat oleh:*
*[Dean Gavrilla Azora Pribadi]*  
XI RPL 3 - [SMK Telkom Malang]  
Tahun Ajaran 2025/2026

---

*Untuk GitHub README.md, Anda tinggal copy paste konten di atas dan tambahkan screenshot dengan format:*

markdown
![Bar Chart](images/bar_chart.png)
![Boxplot](images/boxplot.png)
