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


