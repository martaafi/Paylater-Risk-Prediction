# Paylater-Risk-Prediction
## Pendahuluan

**PDM Paylater** adalah perusahaan fiktif penyedia layanan Buy Now Pay Later (BNPL) yang utamanya mendapatkan pendapatan dengan memberikan pinjaman uang. Salah satu risiko utama dalam praktik ini adalah kemungkinan peminjam gagal membayar pinjamannya, dengan menghentikan pembayaran sesuai kesepakatan. Hal ini akan menyebabkan kerugian keuangan bagi perusahaan.

Untuk mengurangi kerugian tersebut, sangat penting bagi PDM Paylater untuk membuat keputusan yang terinformasi (berbasiskan data) tentang kepada siapa memberikan pinjaman. Pada dasarnya, mereka perlu menilai risiko yang terkait dengan setiap peminjam dan membuat keputusan pemberian pinjaman berdasarkan hal itu.

## Langkah Analisis
- Preprocessing Data meliputi penanganan duplikasi data, inkonsistensi data, dan penanganan missing value.
- Exploratory Data Analysis
- Feature Engineering, yaitu pembuatan fitur baru (`PRE_LATE`, `PAY_HIS`, dan `OVERREQUESTED_CREDIT`) dan encoding data.
- Splitting data `train` menjadi `train` dan `val` dengan proporsi `60:40`
- SMOTE, untuk menangani data yang tidak seimbang.
- Modelling menggunakan algoritma `LogisticRegression`, `LogisticRegressionCV`, `GradientBoostingClassifier`, `HistGradientBoostingClassifier`, `CatBoostClassifier`, `XGBClassifier`, `BernoulliNB`, `GaussianNB`, `KNeighborsClassifier`, `SVC`, `DecisionTreeClassifier`, `AdaBoostClassifier`, `RandomForestClassifier`, dan `QuadraticDiscriminantAnalysis`.
- Pemilihan model terbaik dengan metrik evaluasi `precision`.
- Hyperparametr tuning model terbaik.
- Evaluasi model terbaik dengan data `test`.
- Identifikasi Feature Importance.

## Tools
- Python

## Model terbaik
![image](https://github.com/user-attachments/assets/ca7fc248-a1b4-4114-8d21-154a14326d9c)
![image](https://github.com/user-attachments/assets/ce29d2fa-14d9-4273-9ef5-cc4a4195585c)

Model terbaik untuk prediksi peminjam yang layak diberikan pinjaman atau tidak adalah `RandomForestClassifier` dengan parameter `class_weight`='balanced', `max_depth`=10, dan `n_estimators`=100, dengan nilai `precision` sebesar `0,3`.

## Feature Importance
![image](https://github.com/user-attachments/assets/11bcddfc-9ba6-4680-a73e-1c1e3d4b04a5)

## Kesimpulan
Dari serangkaian proses analisis klasifikasi komprehensif yang telah dilakukan sebelumnya, diperoleh bawa algoritma terbaik untuk memprediksi klien yang pantas untuk diberi pinjaman dan tidak (`FLAG`) adalah `RandomForestClassifier` dengan `precision` sebesar `0,3`. Dengan fitur yang paling berpengaruh dalam prediksi model adalah `PRE_LATE`, `PAY_HIS`, `EXTERNAL_SCORE_1`, `EXTERNAL_SCORE_3`, dan `DAYS_WORK`.

## Rekomendasi

Berdasarkan kesimpulan yang diperoleh, perusahaan disarankan untuk memberikan pinjaman kepada peminjam yang memenuhi kriteria berikut:

- Tidak pernah terlambat melakukan pembayaran
- Tidak memiliki riwayat pembayaran yang buruk atau gagal bayar
- Memiliki durasi kerja yang cukup lama di pekerjaan saat ini sebelum mengajukan pinjaman. Peminjam dengan pekerjaan yang stabil cenderung memiliki risiko gagal bayar lebih rendah.

