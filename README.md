# stage2_finest_project
Summary
Data Cleansing
Pada proses ini, kami berusaha untuk membersihkan data dari missing value, duplicate, outliers, dan imbalance. Tujuannya agar data siap untuk diolah dan bisa lebih mudah dimengerti oleh Machine Learning.
a.	Handle missing value
Dari 16 fitur yang ada, terdapat 4 fitur yang memiliki missing value. Fitur-fitur tersebut ialah duration, campaign, pdays, previous, y. Setelah melakukan analisis terhadap dataset bank, kami memutuskan untuk menghapus baris data yang kosong karena persentase baris kosong tersebut kurang dari 1%. Dengan menghapus baris-baris yang kosong, kami dapat mempertahankan sebagian besar informasi yang ada dalam dataset tanpa mengorbankan jumlah sampel yang signifikan. Pendekatan ini memungkinkan kami untuk melanjutkan analisis dengan dataset yang lebih lengkap dan representatif, yang diharapkan dapat menghasilkan hasil yang lebih akurat dan reliable dalam konteks analisis yang dilakukan terkait dengan data bank tersebut.
b.	Handle duplicated data
Dalam mengelola dataset bank, kami telah melakukan penghapusan data duplikat dengan menggunakan subset kolom 'age', 'job', 'balance', 'loan', 'campaign', dan 'y'. Dengan melakukan penghapusan ini, kami memastikan bahwa setiap entri dalam dataset hanya mewakili satu observasi unik yang tidak memiliki duplikat dengan kombinasi nilai pada kolom-kolom yang disebutkan. Setelah dilakukan drop duplicated dan handle missing value, data yang semula berjumlah 45663 menjadi 41285.
c.	Handle outliers
Berdasarkan analisis dataset Bank tersebut, kami tidak perlu menghapus outlier karena nilai-nilai yang ekstrem masih masuk akal atau dapat dijelaskan secara beralasan. Hal ini menunjukkan bahwa dataset tersebut mengandung variasi yang wajar dan tidak ada observasi yang secara signifikan melenceng dari pola umum yang terlihat. Oleh karena itu, outlier-outlier yang ada dalam dataset bank dapat dianggap sebagai bagian yang sah dari variasi data dan tidak perlu dihapus dalam proses analisis.

d.	Feature Transformation
Pada kesempatan kali ini, kami melakukan log transformation. Log Transformation digunakan pada data yang right-skewed. Distribusi hasil transformasi akan mendekati distribusi normal.
e.	Feature Encoding
Feature Encoding adalah proses mengubah feature categorical menjadi feature numeric. Kami mengubah beberapa fitur yang semula categorical menjadi numerical. 
•	Label Encoding
Kami mengubah fitur marital, education, housing, loan, month yang semula category menjadi numeric.
•	One hot encoding
Melalui teknik ini, kami memecah fitur job menjadi fitur tersendiri.
f.	Handle class imbalance
•	Melakukan pemisahan feature menjadi dua yaitu kategorikal dan numerical.
•	Menghitung matriks korelasi antara fitur menggunakan fungsi ‘.corr()’
•	Melakukan visualisasi data dengan heatmap untuk melihat korelasi
•	Melakukan pemisahan data (split) menjadi data train dan data set
•	Melakukan class imbalance terhadapat fitur target ‘y’ menggunakan oversampling (SMOTE) dan undersampling
 a.	Feature selection
Feature selection dilakukan untuk menentukan fitur dari fitur sebelumnya atau menghapus fitur yang kurang relevan yang akan digunakan untuk modelling. Pada feature selection ini dilakukan analisis heatmap dan pairplot untuk mengetahui apakah terdapat korelasi yang sangat kuat (>0.7) dari data yang akan menyebabkan multikoloniearitas dan menjadikan model tidak optimal.
• Hasil dari heatmap di bawah ini, fitur marital dan age memiliki korelasi yang sangat kuat. Sehingga salah satunya harus dihapus.
b.	Feature extraction
Feature extraction dilakukan untuk membuat fitur baru dari fitur yang sudah ada. Berikut hasil pekerjaan kami:
•	Rasio Balance Terhadap Durasi: Rasio saldo terhadap durasi memberikan perbandingan antara seberapa besar saldo rekening pelanggan dibandingkan dengan durasi kontak yang dilakukan. Jika rasio ini tinggi, dapat menunjukkan bahwa pelanggan dengan saldo yang tinggi cenderung lebih mungkin memberikan tanggapan atau merespons kampanye.
•	Usia Tersegmentasi: Segmentasi usia ini dapat membantu meningkatkan interpretasi model dan juga memungkinkan model untuk mengenali pola atau tren yang spesifik untuk kelompok usia tertentu.
•	Kontak per Hari : dapat mengidentifikasi berapa banyak kontak yang optimal dilakukan dalam satu hari untuk mencapai tujuan tertentu tanpa menyebabkan kelelahan atau kejenuhan pada pelanggan.
•	Kesimpulan Peningkatan Interaksi Sebelumnya :  Dengan tingkat interaksi yang lebih tinggi, ada kemungkinan bahwa pelanggan akan memberikan respons yang lebih baik terhadap kampanye pemasaran saat ini. Mereka mungkin lebih cenderung untuk berlangganan, membeli, atau melakukan tindakan yang diinginkan oleh kampanye tersebut.

c.	Tuliskan minimal 4 feature tambahan
•	Address
Kita dapat mengkategorikan nasabah berdasarkan alamat atau domisili. Dengan begitu, kita dapat melihat pola perilaku pembelian, apakah di suatu kota kecenderungan membeli nasabah tinggi/rendah.
•	Credit score
Fitur ini memberikan informasi apakah nasabah lancar atau tidak dalam membayar hutang. Dengan begitu, kita dapat mengetahui apakah nasabah berpotensi atau tidak membuka deposito berjangka.Rata-rata saldo tahunan
Fitur ini berguna untuk mengetahui rata-rata saldo tahunan nasabah. Dengan begitu, kita dapat memetakan apakah nasabah masuk dalam kategori rata-rata low, medium, atau high. Jika masuk kategori medium/high, besar kemungkinan nasabah berpotensi untuk membuka deposito berjangka.
•	Children
Fitur anak ini berguna untuk mengetahui apakah nasabah sudah memiliki anak atau belum. 
Jumlah anak dapat memengaruhi keputusan seseorang untuk membeli sesuatu, termasuk deposito berjangka. Nasabah yang sudah memiliki anak tentu perlu mengatur keuangannya dengan bijak. Oleh karena itu fitur ini bisa menjadi faktor penting dalam memprediksi konversi.
