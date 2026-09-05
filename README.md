# Klasifikasi Digit MNIST dengan CNN

Proyek ini merupakan tugas mata kuliah Deep Learning untuk melakukan klasifikasi digit tulisan tangan menggunakan dataset MNIST dengan PyTorch.

## Anggota

| Nama            | NIM          |
| --------------- | ------------ |
| Khofifah        | 240441100004 |
| Hilyatul Abidah | 240441100132 |

## Model yang Digunakan

### Model A — CNN Sederhana

Menggunakan 3 blok Conv2D, ReLU, dan MaxPool2D.

Jumlah parameter: **688.138**

### Model B — Residual CNN

Menggunakan Residual Connection (Skip Connection) dan Batch Normalization.

Jumlah parameter: **272.186**

### Model A — AvgPool

Model A dengan MaxPool2d diganti menjadi AvgPool2d sebagai studi ablasi.

Jumlah parameter: **688.138**

## Dataset

Dataset yang digunakan adalah MNIST dengan gambar grayscale berukuran 28×28 piksel.

| Data       | Jumlah |
| ---------- | -----: |
| Training   | 48.000 |
| Validation | 12.000 |
| Testing    | 10.000 |

## Hyperparameter

* Learning Rate: `0.001`
* Epoch: `10`
* Batch Size: `64`
* Optimizer: `Adam`
* Loss Function: `CrossEntropyLoss`

## Hasil

| Model              | Test Loss | Accuracy |
| ------------------ | --------: | -------: |
| Model A – MaxPool  |    0.0315 |   99.22% |
| Model B – Residual |    0.0213 |   99.37% |
| Model A – AvgPool  |    0.0296 |   99.12% |

Model B memperoleh akurasi terbaik sebesar **99.37%**.

Pada studi ablasi, penggunaan MaxPool dan AvgPool menghasilkan performa yang relatif sama pada dataset MNIST.

## Tools

* Python
* PyTorch
* Torchvision
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

## Cara Menjalankan

1. Buka file `DeepLearning.ipynb` menggunakan Google Colab.
2. Aktifkan GPU jika diperlukan.
3. Jalankan semua cell dengan `Runtime → Run all`.
4. Dataset MNIST akan diunduh secara otomatis.

## Struktur File

```text
├── DeepLearning.ipynb
└── README.md
```

## Kesimpulan

Model B dengan Residual Connection memberikan hasil terbaik dengan akurasi **99.37%**. Model A memiliki arsitektur yang lebih sederhana dan waktu training yang lebih cepat. Sementara itu, penggantian MaxPool menjadi AvgPool tidak memberikan perbedaan performa yang signifikan pada dataset MNIST.
