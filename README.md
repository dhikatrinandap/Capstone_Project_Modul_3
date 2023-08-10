## **Business Problem Understanding**
### **Context**
Bike sharing adalah sebuah sistem transportasi dimana sepeda-sepeda yang disediakan oleh penyedia layanan dapat dipinjam dan digunakan oleh masyarakat umum. Sistem ini memungkinkan orang untuk menyewa sepeda untuk jangka waktu tertentu, biasanya beberapa jam atau bahkan beberapa hari.

### **Problem Statement**
Selain bisa memberikan manfaat seperti transportasi ramah lingkungan, solusi kepadatan lalu lintas, aksesbilitas, dan hal lainnya. Para penyedia bike sharing ini mendapatkan suatu tantangan tersendiri yaitu bagaimana untuk mengetahui berapa banyak sepeda yang harus di distribusikan agar sepeda yang tersedia tidak dalam kondisi kekurangan maupun dalam kondisi terlalu banyak.
Menyediakan jumlah sepeda yang cukup dalam berbagai situasi dan kondisi. Jika menyediakan sepeda terlalu banyak, maka akan berdampak pada biaya penyedia. Jika kekurangan jumlah sepeda maka penedia gagal dalam memenuhi kebutuhan dari pengguna.

### **Analytic Approach**
Jadi, yang perlu kita lakukan adalah menganalisis data untuk dapat menemukan pola dari fitur-fitur yang ada, yang membedakan pada kondisi-kondisi tertentu. 
Selanjutnya, kita akan membangun suatu model regresi yang akan membantu penyedia untuk dapat menyediakan 'tool' prediksi jumlah sepeda yang perlu didistribusikan berdasarkan kondisi-kondisi tertentu.

### **Metric Evaluation**
Evaluasi metrik yang akan digunakan adalah RMSE, MAE, dan MAPE, di mana RMSE adalah nilai rataan akar kuadrat dari error, MAE adalah rataan nilai absolut dari error, sedangkan MAPE adalah rataan persentase error yang dihasilkan oleh model regresi. Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi jumlah sepeda yg didistribusikan sesuai dengan limitasi fitur yang digunakan.

### **Conclution**
- Model yang dipilih adalah model XGBosst yang sudah di tranfformasi ke skala logaritmik, kemudian ditransformasi kembali ke fungsi inverse. Parameter tuning terbaik pada model XGBoost ini adalah:
    - 'model__regressor__subsample': 0.8,
    - 'model__regressor__reg_alpha': 1.0,
    - 'model__regressor__n_estimators': 195,
    - 'model__regressor__max_depth': 10,
    - 'model__regressor__learning_rate': 0.12,
    - 'model__regressor__colsample_bytree': 0.9
  - Hyperpamater tuning kedua membuat performa model meingkat:
    - RMSE, MAE & MAPE sebelum tuning : 41.074, 25.589, 24.964%
    - RMSE, MAE & MAPE setelah tuning 1 : 45.089, 27.670, 26.445%
    - RMSE, MAE & MAPE setelah tuning 2 : 39.582, 24.215, 24.843%
