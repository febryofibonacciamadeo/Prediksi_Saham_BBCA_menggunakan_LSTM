# Prediksi Saham BBCA menggunakan LSTM

Proyek ini melakukan prediksi harga saham **BBCA (Bank Central Asia)** menggunakan model *Long Short-Term Memory* (LSTM), sebuah arsitektur *Recurrent Neural Network* (RNN) yang cocok untuk data deret waktu (*time series*).

## Deskripsi

Harga saham merupakan data deret waktu yang memiliki pola historis dan tren. Model LSTM dipilih karena kemampuannya menangkap dependensi jangka panjang dalam data sekuensial, sehingga cocok digunakan untuk memprediksi pergerakan harga saham BBCA berdasarkan data historis.

## Struktur Repository

```
Prediksi_Saham_BBCA_menggunakan_LSTM/
├── dataset/                  # Data historis harga saham BBCA
├── bbca_forecast_model.h5    # Model LSTM terlatih (format Keras/TensorFlow)
└── code.ipynb                # Notebook utama: preprocessing, training, evaluasi & prediksi
```

## Alur Kerja (Workflow)

1. **Data Loading:** memuat data historis harga saham BBCA dari folder `dataset/`.
2. **Data Preprocessing:** pembersihan data, normalisasi/scaling (mis. MinMaxScaler), dan pembentukan *sliding window* untuk data sekuensial.
3. **Train-Test Split:** membagi data menjadi data latih dan data uji berdasarkan urutan waktu.
4. **Model Building:** membangun arsitektur LSTM menggunakan TensorFlow/Keras.
5. **Training:** melatih model pada data historis.
6. **Evaluation:** mengevaluasi performa model menggunakan metrik seperti RMSE/MAE, serta visualisasi harga aktual vs prediksi.
7. **Model Saving:** model tersimpan sebagai `bbca_forecast_model.h5`.

## Library yang Digunakan

- Python
- Jupyter Notebook
- TensorFlow / Keras (LSTM)
- pandas & numpy
- scikit-learn (preprocessing/scaling & metrik evaluasi)
- matplotlib (visualisasi hasil prediksi)

## Cara Menjalankan

1. Clone repository ini:
   ```bash
   git clone https://github.com/febryofibonacciamadeo/Prediksi_Saham_BBCA_menggunakan_LSTM.git
   cd Prediksi_Saham_BBCA_menggunakan_LSTM
   ```
2. Install dependensi:
   ```bash
   pip install numpy pandas scikit-learn tensorflow matplotlib jupyter
   ```
3. Jalankan notebook:
   ```bash
   jupyter notebook code.ipynb
   ```
4. Atau langsung memuat model terlatih untuk prediksi tanpa training ulang:
   ```python
   from tensorflow.keras.models import load_model
   model = load_model("bbca_forecast_model.h5")
   ```

## Hasil

Hasil prediksi divisualisasikan dalam bentuk grafik perbandingan antara harga aktual dan harga hasil prediksi model LSTM. Lihat notebook `code.ipynb` untuk detail metrik evaluasi (RMSE/MAE) dan grafiknya.

## Disclaimer

Model dan hasil prediksi pada repository ini dibuat untuk tujuan pembelajaran/riset, **bukan** merupakan saran atau rekomendasi investasi/trading. Pergerakan harga saham dipengaruhi banyak faktor yang tidak sepenuhnya dapat ditangkap oleh model historis.
