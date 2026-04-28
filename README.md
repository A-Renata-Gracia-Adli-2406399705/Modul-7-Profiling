# Performance Testing

## Test Plan 1 (/all-student)
1. View Results Tree
   ![all-student view results tree](/assets/images/test_plan_1 results tree.png)
2. View Results in Table
   ![all-student view results in table](/assets/images/test_plan_1 results in table.png)
3. Summary Report
   ![all-student summary report](/assets/images/test_plan_1 summary report.png)
4. Graph Results
   ![all-student graph results](/assets/images/test_plan_1 graph results.png)
5. CLI
   ![all-student cli results](/assets/images/test_plan_1 cli.png)
6. After Optimizing
   ![all-student after optimizing](/assets/images/all-student after optimizing.png)


## Test Plan 2 (/all-student-name)
1. View Results Tree
   ![all-student-name view results tree](/assets/images/test_plan_2 results tree.png)
2. View Results in Table
   ![all-student-name view results in table](/assets/images/test_plan_2 results in table.png)
3. Summary Report
   ![all-student-name summary report](/assets/images/test_plan_2 summary report.png)
4. Graph Results
   ![all-student-name graph results](/assets/images/test_plan_2 graph results.png)
5. CLI
   ![all-student-name cli results](/assets/images/test_plan_2 cli.png)
6. After Optimizing
   ![all-student-name after optimizing](/assets/images/all-student-name after optimizing.png)


## Test Plan 3 (/highest-gpa)
1. View Results Tree
   ![highest-gpa view results tree](/assets/images/test_plan_3 results tree.png)
2. View Results in Table
   ![highest-gpa view results in table](/assets/images/test_plan_3 results in table.png)
3. Summary Report
   ![highest-gpa summary report](/assets/images/test_plan_3 summary report.png)
4. Graph Results
   ![highest-gpa graph results](/assets/images/test_plan_3 graph results.png)
5. CLI
   ![highest-gpa cli results](/assets/images/test_plan_3 cli.png)
6. After Optimizing
   ![highest-gpa after optimizing](/assets/images/highest-gpa after optimizing.png)


## Hasil Performance Testing After Optimizing

Hasil performance testing menunjukkan adanya peningkatan performance pada seluruh endpoint yang ditest.

- Endpoint `/all-student` mengalami penurunan response time dari yang average-nya 57751 menjadi 21641.
- Endpoint `/all-student-name` mengalami penurunan response time dari yang average-nya 1005 menjadi 303.
- Endpoint `/highest-gpa` mengalami penurunan response time dari yang average-nya 440 menjadi 152.

Dapat disimpulkan bahwa optimization yang dilakukan berhasil meningkatkan performance aplikasi, yang ditandai dengan penurunan response time dibandingkan sebelum optimization.


# Performance Optimization
1. /all-student
   ![cpu time getallstudentswithcourses](/assets/images/cpu time getallstudentswithcourses.png)
2. /all-student-names
   ![cpu time joinstudentnames](/assets/images/cpu time joinstudentnames.png)
3. /highest-gpa
   ![cpu time findstudentwithhighestgpa](/assets/images/cpu time findstudentwithhighestgpa.png)


# Reflection

1. JMeter digunakan untuk melakukan performance testing dari sisi eksternal dengan mensimulasikan banyak pengguna yang mengakses aplikasi secara bersamaan. Hasilnya berupa response time, throughput, error rate, dll.
Sedangkan IntelliJ Profiler digunakan untuk menganalisis performa dari sisi internal aplikasi. Profiler memberikan informasi detail mengenai method mana yang paling banyak menggunakan CPU time atau resource sehingga memudahkan dalam menemukan bottleneck pada kode.


2. Profiling membantu mengidentifikasi bagian kode yang paling banyak mengonsumsi resource, seperti CPU time. Dengan melihat flame graph dan method list, kita dapat mengetahui method mana yang menjadi bottleneck sehingga optimization dapat difokuskan pada bagian tersebut.


3. Iya, menurut saya, IntelliJ Profiler sangat efektif dalam membantu menganalisis performa aplikasi karena visualisasi seperti flame graph memudahkan dalam memahami alur eksekusi program dan menemukan bagian yang tidak efisien sehingga proses debugging dan optimization menjadi lebih terarah.


4. Beberapa tantangannya yaitu:
- Hasil pengujian yang tidak konsisten karena faktor-faktor seperti spesifikasi laptop atau beban sistem
- Waktu eksekusi yang lama saat data yang digunakan cukup besar
- Kesulitan memahami flame graph di awal

Cara mengatasinya:
- Melakukan pengujian beberapa kali untuk mendapatkan hasil yang lebih stabil
- Mengurangi jumlah data saat development tapi tanpa menghilangkan esensi testing
- Memahami dasar cara kerja profiler secara bertahap


5. Manfaatnya yaitu:
- Dapat mengetahui method yang paling memakan resource
- Membantu menemukan bottleneck secara spesifik
- Mempermudah proses optimization karena berbasis data, bukan asumsi


6. Perbedaan hasil antara JMeter dan Profiler dapat terjadi karena JMeter mengukur performa dari sisi pengguna (response time), sedangkan Profiler mengukur penggunaan resource internal (CPU time).
Cara mengatasi kalau resultsnya tidak konsisten adalah hasil dari keduanya digunakan secara komplementer. Profiler digunakan untuk menemukan sumber masalah, sedangkan JMeter digunakan untuk memvalidasi apakah optimization benar-benar meningkatkan performance dari sisi pengguna.


7. Strategi optimization yang dilakukan yaitu:
- Mengurangi jumlah query database (menghindari N+1 query)
- Memanfaatkan query langsung dari database (misalnya sorting di database)
- Menggunakan struktur data yang lebih efisien seperti StringBuilder

Untuk memastikan perubahan tidak merusak fungsionalitas, maka:
- Melakukan testing ulang endpoint setelah perubahan
- Membandingkan hasil output sebelum dan sesudah optimization
- Menjalankan kembali performance testing untuk memastikan aplikasi tetap berjalan dengan benar