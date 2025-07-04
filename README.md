# Clustering_Submission_Akhir_BMLP_Briyan_Yehezkhiel

# Analisis dan Segmentasi Pelanggan Menggunakan K-Means Clustering

## Latar Belakang

Proyek ini bertujuan untuk memahami perilaku pelanggan dalam bisnis ritel melalui segmentasi menggunakan metode unsupervised learning, khususnya clustering K-Means. Hasil segmentasi diharapkan dapat memberikan insight berharga untuk strategi pemasaran yang lebih tepat sasaran, program loyalitas, dan optimasi layanan pelanggan.

## Dataset

Dataset yang digunakan berisi informasi transaksi pelanggan, termasuk:
- TransactionID
- AccountID
- TransactionAmount
- TransactionDate
- TransactionType
- Location
- DeviceID
- IP Address
- MerchantID
- Channel
- CustomerAge
- CustomerOccupation
- TransactionDuration
- LoginAttempts
- AccountBalance
- PreviousTransactionDate

Dataset diambil dari sumber yang disediakan ([link drive](https://drive.google.com/drive/folders/1Zs7VmPZ-jNwsRlMKH65Ea-LApSwx6lKx?usp=drive_link)).

## Langkah-langkah Analisis

Proyek ini mengikuti langkah-langkah berikut:

1.  **Import Library**: Mengimpor pustaka Python yang diperlukan (pandas, seaborn, matplotlib, joblib, sklearn).
2.  **Memuat Dataset**: Memuat dataset, menampilkan 5 baris pertama, memeriksa informasi data (jumlah baris/kolom, tipe data), dan menampilkan statistik deskriptif.
3.  **Pembersihan dan Pra Pemrosesan Data**:
    *   Mengecek data hilang (`isnull().sum()`) dan data duplikat (`duplicated().sum()`).
    *   Melakukan feature scaling pada fitur numerik menggunakan `MinMaxScaler`.
    *   Melakukan feature encoding pada fitur kategorikal menggunakan `LabelEncoder`.
    *   Menghapus kolom 'ID' dan 'IP Address'.
    *   (Opsional Skilled) Menangani data yang hilang dengan `dropna()` dan menghapus data duplikat dengan `drop_duplicates()`.
    *   (Opsional Advanced) Melakukan visualisasi boxplot untuk mendeteksi outlier dan melakukan binning pada fitur 'TransactionAmount' dan 'CustomerAge', kemudian meng-encode hasil binning.
4.  **Membangun Model Clustering**:
    *   Menggunakan Elbow Method (`KElbowVisualizer`) untuk menentukan jumlah cluster optimal.
    *   Membangun model K-Means Clustering (`KMeans`) dengan jumlah cluster yang dipilih.
    *   Menyimpan model K-Means.
    *   (Opsional Skilled) Menghitung dan menampilkan Silhouette Score.
    *   (Opsional Skilled) Membuat visualisasi hasil clustering menggunakan PCA.
    *   (Opsional Advanced) Membangun model clustering menggunakan data yang telah direduksi dimensinya oleh PCA dan menyimpan model PCA.
5.  **Interpretasi Cluster**:
    *   Menambahkan label cluster ke dataframe.
    *   Melakukan analisis deskriptif (mean, min, max untuk numerik; mode untuk kategorikal) untuk setiap cluster.
    *   (Opsional Skilled) Melakukan inverse transform pada fitur numerik dan kategorikal untuk interpretasi dalam skala asli.
    *   Melakukan analisis deskriptif kembali pada data yang sudah di-inverse transform untuk menjelaskan karakteristik tiap cluster.
6.  **Mengeksport Data**:
    *   Mengganti nama kolom cluster menjadi 'Target'.
    *   Menyimpan dataframe hasil clustering ke file CSV (`data_clustering.csv`).
    *   (Opsional Advanced) Menyimpan dataframe hasil clustering dengan data yang sudah di-inverse transform ke file CSV (`data_clustering_inverse.csv`).

## Hasil

Notebook ini menghasilkan:
- Model K-Means Clustering (`model_clustering.h5`)
- (Opsional Advanced) Model K-Means Clustering pada data PCA (`PCA_model_clustering.h5`)
- Dataset dengan label cluster (`data_clustering.csv`)
- (Opsional Skilled/Advanced) Dataset dengan label cluster dan fitur yang di-inverse transform (`data_clustering_inverse.csv`)
- Visualisasi Elbow Method, boxplot (opsional Advanced), dan hasil clustering menggunakan PCA (opsional Skilled).
- Analisis deskriptif karakteristik setiap cluster.

## Cara Menjalankan Notebook

1.  Buka notebook di Google Colab.
2.  Pastikan Anda memiliki akses ke dataset yang disebutkan.
3.  Jalankan setiap cell secara berurutan.
