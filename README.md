# Proyek Klasifikasi Gambar Menggunakan CNN (Sequential Model)

## Informasi Pengembang
- **Nama**: Ahmad Latif Aulia Rahman  
- **Email**: ahmadlatifar10@gmail.com  
- **ID Dicoding**: zergavos  

---

## Deskripsi Proyek
Proyek ini merupakan implementasi **image classification** menggunakan **Convolutional Neural Network (CNN)** dengan **TensorFlow dan Keras**.  
Model dibangun **menggunakan arsitektur Sequential API** sesuai dengan kriteria utama Dicoding, serta **wajib menyertakan Conv2D dan Pooling Layer**.

Dataset yang digunakan adalah **Intel Image Classification Dataset**, yang terdiri dari beberapa kelas citra pemandangan alam.

---

## Tujuan Proyek
- Membangun model klasifikasi gambar berbasis CNN
- Menggunakan **Sequential Model**
- Mengimplementasikan **Conv2D dan Pooling Layer**
- Melatih dan mengevaluasi performa model
- Melakukan konversi model ke **SavedModel**, **TFLite**, dan **TensorFlow.js**

---

## Dataset
- **Sumber**: Kaggle – Intel Image Classification
- **Jumlah kelas**: 6
- **Pembagian data**:
  - Training: 80%
  - Validation: 10%
  - Testing: 10%

Dataset diproses melalui:
- Subsampling jumlah data per kelas
- Resize gambar ke 224x224
- Normalisasi dan batching menggunakan `tf.data`

---

## Arsitektur Model
Model dibangun menggunakan **tf.keras.Sequential()** dengan susunan utama sebagai berikut:

- Input Layer (224x224x3)
- Data Augmentation
- Conv2D
- MaxPooling2D
- Transfer Learning (MobileNetV2 tanpa top layer)
- Global Average Pooling
- Dense Layer
- Dropout
- Output Layer (Softmax)

Model memenuhi seluruh kriteria berikut:
- Menggunakan **Sequential API**
- Menggunakan **Conv2D**
- Menggunakan **Pooling Layer**
- Transfer learning digunakan tanpa melanggar struktur Sequential

---

## Proses Training
- Optimizer: Adam
- Learning Rate: 0.0001
- Loss Function: Sparse Categorical Crossentropy
- Epoch: Maksimal 10
- Callback: EarlyStopping (monitor validation accuracy)

---

## Evaluasi Model
Evaluasi dilakukan menggunakan **data testing** yang terpisah dari data training dan validation.

Metrik yang digunakan:
- Accuracy
- Loss

Hasil training divisualisasikan dalam bentuk grafik:
- Training vs Validation Accuracy
- Training vs Validation Loss

---

## Konversi Model
Model yang telah dilatih dikonversi ke beberapa format:

### 1. SavedModel
Digunakan sebagai format utama dan dasar konversi lanjutan.

### 2. TensorFlow Lite (TFLite)
Digunakan untuk deployment pada perangkat mobile dan embedded system.

### 3. TensorFlow.js
Digunakan untuk deployment model di lingkungan web.

---

## 📂 Struktur Folder
submission/
├── saved_model/
│ ├── assets/
│ ├── variables/
│ ├── saved_model.pb
│ └── fingerprint.pb
│
├── tflite/
│ ├── model.tflite
│ └── label.txt
│
├── tfjs_model/
│ ├── model.json
│ └── group*.bin
│
├── README.md
├── requirements.txt
├── notebook.ipynb

---

## File Pendukung
- `requirements.txt`  
  Berisi daftar library yang digunakan dalam proyek.

---

## Cara Menjalankan Proyek
1. Jalankan seluruh cell notebook secara berurutan
2. Pastikan dataset berhasil terunduh
3. Training model hingga selesai
4. Lakukan evaluasi
5. Jalankan tahap konversi model

---

## Kesimpulan
Proyek ini berhasil membangun model klasifikasi gambar menggunakan **CNN dengan Sequential API**, memenuhi seluruh kriteria utama Dicoding, serta berhasil dikonversi ke berbagai format untuk kebutuhan deployment.

---

## Catatan
Proyek ini dibuat untuk keperluan pembelajaran dan submission kelas Dicoding.