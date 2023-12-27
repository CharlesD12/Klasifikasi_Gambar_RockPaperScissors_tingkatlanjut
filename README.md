#Klasifikasi_Gambar_RockPaperScissors_tingkatlanjut
Proyek yang telah saya kerjakan ini merupakan model deep learning yang mengklasifikasikan gambar gerakan tangan menjadi batu, kertas, atau gunting. Kode ini menggunakan pustaka TensorFlow dan Keras.

Pertama, kode ini menginstal paket Python yang diperlukan dan mengimpor modul yang diperlukan. Kemudian, kode ini mengunduh file zip yang berisi gambar gerakan tangan dari repositori GitHub dan mengekstraknya ke direktori lokal.

Gambar dibagi menjadi set pelatihan dan validasi. Direktori untuk set ini dibuat, dan gambar disalin ke direktori yang sesuai.

Objek ImageDataGenerator dibuat untuk augmentasi data pada set pelatihan dan satu lagi untuk set validasi. Generator ini memuat gambar dari direktori yang ditentukan, dan mengubahnya menjadi tensor titik mengambang. 
Mereka juga mengubah ukuran gambar menjadi 150x150 piksel dan mengatur ukuran batch menjadi 32.

Arsitektur model didefinisikan menggunakan API Sequential Keras. Ini adalah Jaringan Saraf Konvolusional (CNN) dengan tiga lapisan konvolusional, masing-masing diikuti oleh lapisan pooling maksimum. 
Setelah basis konvolusional, fitur diratakan dan dilewatkan melalui lapisan dropout untuk regularisasi, dan kemudian dua lapisan padat. Lapisan terakhir menggunakan fungsi aktivasi softmax untuk klasifikasi multi-kelas.

Model dikompilasi dengan optimizer Adam dan fungsi kerugian cross-entropy kategorikal karena ini adalah masalah klasifikasi multi-kelas. Kinerja model dievaluasi menggunakan metrik akurasi.

Model dilatih pada set pelatihan selama 20 epoch dengan ukuran batch 200. Set validasi digunakan untuk mengevaluasi model setelah setiap epoch. Pelatihan berhenti jika akurasi melebihi 98% karena callback yang ditentukan.

Setelah pelatihan, akurasi dan kerugian model selama epoch diplot.

Terakhir, model digunakan untuk memprediksi kelas gambar yang diunggah. Gambar dimuat, diubah ukurannya menjadi 150x150 piksel, diubah menjadi array, dan kemudian dilewatkan ke model untuk prediksi. Kelas yang diprediksi dicetak.
