# CIFAR-10 classification using SVM Linear Method
## Dataset
Dataset CIFAR-10 terdiri dari 60.000 citra berwarna dengan ukuran 32 x 32 pixel RGB.
Setiap *image* memiliki 32 x 32 x 3 = 3072 fitur.
Dataset terdiri dari 10 kelas yaitu 'plane', 'auto','bird', 'cat', 'deer', 'dog', 'frog', 'horse', 'ship', 'truck' dengan 6000 citra untuk setiap kelas.
Dataset tersebut telah dibagi menjadi 50.000 data *training* dan 10.000 data *testing* sehingga terdapat 5.000 data *train* dan 1.000 data *test* untuk setiap kelas.
Pengambilan dataset dilakukan dengan menggunakan modul myutils . Setelah itu dilakukan inisialisasi pembagian data *train* dan data *test* untuk pembuatan model selanjutnya.
## Praproses Data
Dataset memiliki 4 kelas yang bukan merupakan kelas hewan yaitu plane, automobile, ship, dan truck, sehingga data *train* dan data *test* yang termasuk dalam kelas tersebut
harus dihapus terlebih dahulu sehingga mendapatkan kelas hewan saja. 
Penghapusan data dilakukan menggunakan *package* numpy. 
Setelah itu dilakukan transformasi gambar ke dalam format *grayscale* menggunakan *package* opencv dan ditampilkan 10 *random sample* dari data
*train* sebagai berikut :
![alt text](https://user-images.githubusercontent.com/46989222/84618002-f1341200-aefa-11ea-968d-8859e4f667b7.PNG)
## Ekstraksi Ciri ( *Feature Extraction* )
Ekstraksi fitur dilakukan menggunakan Histogram of Oriented Gradient (HOG) dan dilakukan *decompress* menggunakan PCA.
Ekstraksi fitur ini menggunakan *package* skimage.feature dari scikit-image .
Ekstraksi fitur menggunakan HOG menghasilkan beberapa *random sample* sebagai berikut :
![alt text](https://user-images.githubusercontent.com/46989222/84617990-ee392180-aefa-11ea-89af-db71718f1dcf.PNG)
Setelah itu dilakukan dekompresi ke dalam 2D menggunakan metode PCA yang dilakukan dengan menggunakan *package* sklearn.
Pada tahap ini menghasilkan visualisasi sebagai berikut :

<img src="https://user-images.githubusercontent.com/46989222/84617996-ef6a4e80-aefa-11ea-8c86-90abdf708544.png" width="300" height="300">

## Klasifikasi
Klasifikasi dilakukan menggunakan package Keras, metode SVM Linear dilakukan menggunakan package sklearn.svm.

## Hasil Klasifikasi
Klasifikasi SVM menghasilkan akurasi sebesar **52,05 %** dengan *Confusion matrix* sebagai berikut:
![alt text](https://user-images.githubusercontent.com/46989222/84617988-ec6f5e00-aefa-11ea-9d46-1b1a437cdfdd.PNG)
