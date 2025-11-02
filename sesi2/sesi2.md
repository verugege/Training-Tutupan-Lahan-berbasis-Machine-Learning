# Feature Engineering dan Persiapan Data Training
Pemetaan Tutupan Lahan dan Pembuatan Peta Kreatif Berbasis Machine Learning (Studi Kasus: Mangrove dan Tutupan Lahan Lainnya) / Meeting / Feature Engineering dan Persiapan Data Training


Sesi ini berfokus pada tahap feature engineering untuk menyiapkan dataset berkualitas yang siap digunakan dalam proses machine learning. Peserta akan mempelajari karakteristik spektral dari berbagai kelas tutupan lahan dan ekosistem mangrove, serta bagaimana mengubah data citra menjadi variabel bermakna melalui pembuatan spectral indices seperti NDVI, MNDWI, NDBI, NDMI, dan CMRI. Selanjutnya, peserta akan menggabungkan original bands dengan indeks spektral untuk membentuk feature matrix yang menjadi masukan utama bagi model pembelajaran mesin. Sesi ini juga mencakup strategi sampling yang tepat menggunakan metode stratified random sampling, pembuatan training samples di QGIS, dan pembagian data menjadi training dan testing set. Dengan mengikuti sesi ini, peserta akan memahami langkah-langkah kunci dalam membangun dataset representatif untuk model klasifikasi berbasis citra satelit.

## Membuat Loop untuk plotting semua spectral index sekaligus:

List nama spectral index

spectral_index_names = ['NDVI', 'NDBI', 'MNDWI', 'NDMI', 'CMRI']


<img width="534" height="390" alt="Untitled" src="https://github.com/user-attachments/assets/f7093cf9-cacd-4a78-8799-e8e06a634bf2" />
<img width="534" height="390" alt="Untitled" src="https://github.com/user-attachments/assets/4f66e40d-bace-4192-abd9-9f113aad9988" />
<img width="534" height="390" alt="Untitled-1" src="https://github.com/user-attachments/assets/6490ce93-9d21-4d5a-8ec6-6716596875fa" />
<img width="534" height="390" alt="Untitled" src="https://github.com/user-attachments/assets/99efd440-c310-44bf-979a-e431ac4f1626" />
<img width="534" height="390" alt="Untitled-1" src="https://github.com/user-attachments/assets/db991886-d1fc-4208-b979-8e8a5e3912b6" />


## Membuat Spectral Reflectance Curves setiap kelas
<img width="1289" height="590" alt="Untitled" src="https://github.com/user-attachments/assets/e2c7aec4-d191-464b-9017-f915c86d7c5a" />
