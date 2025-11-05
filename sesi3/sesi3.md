Sesi 3 :
- Pengenalan XGBoost dan Perbandingan dengan Algoritma Lain
- Training Model XGBoost
- Accuracy Assessment dan Confusion Matrix
- Hyperparameter Tuning untuk Optimasi Model
- Feature Importance dan Error Analysis

1. XGBoost Training dan Accuracy Assessement

Seperti telah dijelaskan sebelumnya, pada hari kedua data sampel telah dibagi menjadi dua bagian, yaitu 80% untuk training dan 20% untuk testing. Seluruh data tersebut telah disimpan dalam format .npy, sehingga pada tahap ini kita hanya perlu memanggilnya kembali untuk proses pelatihan model dan evaluasi akurasi.

Pada sesi hari ketiga, peserta akan mempelajari penggunaan algoritma machine learning Extreme Gradient Boosting (XGBoost) dengan memanfaatkan library xgboost di Python. Library ini dirancang secara khusus untuk memudahkan pengguna dalam mengimplementasikan algoritma XGBoost yang dikenal efisien, fleksibel, dan portabel. Library xgboost mengimplementasikan algoritma pembelajaran mesin berbasis kerangka kerja Gradient Boosting.

2. Hyperprameter Tuning

Hyperparameter adalah “pengaturan dari luar” sebuah model machine learning. Nilainya tidak dipelajari otomatis dari data, tapi ditentukan oleh kita sebelum model dijalankan

jadi intinya Hyperparameter tuning adalah proses mencoba berbagai kombinasi pengaturan hyperparameter untuk mencari yang paling optimal.

Tujuannya supaya model bisa belajar dengan baik → akurasi tinggi, error kecil, dan tidak overfitting.

<img width="787" height="530" alt="image" src="https://github.com/user-attachments/assets/983aced6-7ffa-4753-8009-a686424725fc" />

2.1 Melakukan Hyperparameter Tuning secara manual

Terdapat beebrapa parameter yang dapat kita definiskan untuk melakukan hyperparameter tuning. Beberapa paramater penting yang dapat kita definisikan adalah: n_estimator, max_depth, eta, gamma, subsample, dan colsample_bytree.

    n_estimators, number of trees atau jumlah pohon yang ada didalam model (default=100)
    max_depth, mengntrol maximum depth of tress pada model (default=6)
    eta, eta atau learning rate yang mengontrol step size dimana optimizer akan membuat updates kedalam nilai bobot/weights (default=0.3)
    gamma, atau min_split_loss adalah minimum loss reduction yang diperlukan untuk membuat partisi lebih lanjut pada leaf node of the tree (default=0)
    subsample, Parameter subsampel mengendalikan fraksi pengamatan yang digunakan untuk setiap pohon (default=1)
    colsample_bytree, Parameter colsample_bytree mengontrol fraksi fitur yang digunakan untuk setiap pohon (default=1)

Kita bisa melihat hasil dari parameter yang kita definisikan secara manual menghasilkan akurasi yang sedikit lebih jelek dari hasil model secara default. Oleh karena itu, kita dapat menggunakan metode gridsearch untuk melakukan hyperparameter tuning secara otomatis

2.2 Hyperparameter tuning menggunakan GridSearchCV
untuk mempermudah, untuk tuning disini kita akan mencoba menggunakan GridSearchCV. GridSearchCV adalah metode di scikit-learn untuk melakukan pencarian hyperparameter terbaik dengan cara mencoba semua kombinasi yang mungkin dari daftar hyperparameter yang kita tentukan.



bisa di lihat pada pemberitahuan output nya bahwa:

    324 candidates → ada 324 kombinasi parameter berbeda yang didefinisikan di dalam param_grid. Jadi GridSearchCV akan mencoba melatih MLP dengan 324 konfigurasi berbeda.
    5 folds → setiap kombinasi parameter diuji menggunakan 5-fold cross-validation. Jadi, untuk satu kombinasi parameter, model akan dilatih dan divalidasi 5 kali dengan pembagian data yang berbeda.
    totalling 1620 fits → total keseluruhan proses pelatihan (fit) yang dilakukan adalah 324 × 5 = 1620 Dengan kata lain, GridSearchCV sedang melakukan 1620 kali training dan evaluasi untuk mencari kombinasi parameter terbaik dengan hasil akurasi paling tinggi.


<img width="1733" height="764" alt="image" src="https://github.com/user-attachments/assets/371e798d-6f49-4525-817c-7d8aab7f2b48" />
