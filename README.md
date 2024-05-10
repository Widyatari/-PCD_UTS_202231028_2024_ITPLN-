
# PROJECT UTS PENGOLAHAN CITRA

Nama : Widya Tari
Nim  : 202231028

#import cv2
#import numpy as np
#from matplotlib import pyplot as plt

Pertama, kita mengimpor pustaka yang diperlukan:
- cv2: Pustaka OpenCV (Open Source Computer Vision Library) untuk pemrosesan gambar dan komputer.
- numpy as np: NumPy, pustaka Python yang digunakan untuk bekerja dengan array dan matriks besar dari data numerik.
- from matplotlib import pyplot as plt: Matplotlib, pustaka Python untuk membuat visualisasi seperti plot, grafik, dan gambar.

Kemudian, kita bisa menggunakan OpenCV untuk membaca gambar dari file atau memanipulasi gambar yang ada. NumPy digunakan untuk melakukan operasi matriks pada gambar, seperti perhitungan matematis atau manipulasi piksel. Terakhir, matplotlib digunakan untuk menampilkan gambar dalam bentuk plot.

#import cv2
#import numpy as np
#import matplotlib.pyplot as plt
#import matplotlib.image as img

#%matplotlib inline

- import cv2: Ini mengimpor pustaka OpenCV (Open Source Computer Vision Library), yang sangat populer untuk memproses gambar dan video. OpenCV memiliki berbagai fungsi yang memungkinkan kita untuk melakukan berbagai operasi pada gambar, seperti membaca, menulis, manipulasi, deteksi objek, dan banyak lagi.
- import numpy as np: Ini mengimpor NumPy, pustaka Python yang kuat untuk melakukan operasi pada array dan matriks. NumPy sering digunakan dalam pemrosesan gambar untuk manipulasi dan analisis data.
- import matplotlib.pyplot as plt: Ini mengimpor modul pyplot dari matplotlib, yang digunakan untuk membuat plot dan visualisasi data. Dalam konteks ini, kita menggunakan matplotlib untuk menampilkan gambar.
- import matplotlib.image as img: Ini mengimpor modul image dari matplotlib, yang menyediakan fungsi-fungsi untuk membaca dan menulis gambar dalam berbagai format.
- %matplotlib inline: Ini adalah magic command untuk Jupyter Notebook yang memastikan bahwa output dari matplotlib akan ditampilkan secara langsung di dalam notebook, bukan dalam jendela popup terpisah.
Jadi, secara keseluruhan, coding tersebut digunakan untuk melakukan pengolahan gambar, termasuk membaca, memanipulasi, dan menampilkan gambar. 

#color_image = img.imread('namasaya.jpg')
#plt.imshow(color_image)

ketiga adalah source cuntuk membaca gambar dari file dengan nama 'namasaya.jpg', kemudian menampilkannya menggunakan matplotlib. 
- color_image = img.imread('namasaya.jpg') Ini adalah baris kode yang membaca gambar 'namasaya.jpg' dari sistem file dan menyimpannya dalam variabel color_image. Fungsi img.imread() dari modul matplotlib.image digunakan untuk membaca gambar dari file dan mengembalikan representasi matriks dari gambar tersebut. Dalam kasus ini, gambar dibaca dalam format warna.
- plt.imshow(color_image): adalah baris kode yang menampilkan gambar yang telah dibaca menggunakan matplotlib. Fungsi plt.imshow() digunakan untuk menampilkan gambar di dalam plot. Argumen yang diberikan adalah matriks gambar yang telah dibaca sebelumnya.

#r = color_image[:,:,0]
#g = color_image[:,:,1]
#b = color_image[:,:,2]

#f,(c1,c2,c3,c4) = plt.subplots(1,4,figsize = (20,10))

#c1.set_title('Gambar Asli')
#c1.imshow(color_image)
#c1.axis('off')

#c2.set_title('Merah')
#c2.imshow(r,cmap="gray")
#c2.axis('off')

#c3.set_title('Hijau')
#c3.imshow(g,cmap="gray")
#c3.axis('off')

#c4.set_title('Biru')
#c4.imshow(b,cmap="gray")
#c4.axis('off')

keempat yaitu untuk membagi citra warna menjadi tiga saluran warna utama (merah, hijau, dan biru) dan menampilkannya secara terpisah.kita menggunakan: 
- r = color_image[:,:,0], g = color_image[:,:,1] 
b = color_image[:,:,2]: untuk memisahkan citra warna menjadi tiga saluran warna utama, yaitu merah, hijau, dan biru. Dalam representasi citra dalam format RGB (Red-Green-Blue), setiap piksel memiliki tiga komponen warna yang mewakili intensitas warna merah, hijau, dan biru. Dengan menggunakan slicing pada matriks color_image, kita dapat memisahkan setiap saluran warna menjadi matriks tersendiri.
- f,(c1,c2,c3,c4) = plt.subplots(1,4,figsize = (20,10)): ini berfungsi untuk membuat sebuah plot dengan empat subplot. Subplot pertama (c1) akan menampilkan gambar asli, sedangkan subplot kedua (c2), ketiga (c3), dan keempat (c4) akan menampilkan saluran warna merah, hijau, dan biru secara terpisah. Ukuran keseluruhan plot ditentukan oleh figsize = (20,10).
- c1.set_title('Gambar Asli'), c2.set_title('Merah'), c3.set_title('Hijau'), c4.set_title('Biru'): kode ini yang memberikan judul untuk masing-masing subplot.
- c1.imshow(color_image), c2.imshow(r,cmap="gray"), c3.imshow(g,cmap="gray"), c4.imshow(b,cmap="gray"): Ini adalah baris kode yang menampilkan gambar dan saluran warna merah, hijau, dan biru dalam subplot yang sesuai. Pada subplot yang menampilkan saluran warna, kita menggunakan argumen cmap="gray" untuk menampilkan gambar dalam skala abu-abu, karena masing-masing saluran warna tidak memiliki informasi warna penuh.
- c1.axis('off'), c2.axis('off'), c3.axis('off'), c4.axis('off'): yang menonaktifkan tampilan sumbu (axis) pada setiap subplot.

#color_image = cv2.imread('namasaya.jpg')
#color_image = cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB)
#histogram_biru = cv2.calcHist([b],[0],None,[256],[0,256])
#histogram_hijau = cv2.calcHist([g],[0],None,[256],[0,256])
#histogram_merah = cv2.calcHist([r],[0],None,[256],[0,256])
#histogram_warna = cv2.calcHist([color_image],[0,1,2],None,[256,256,256],[0,256,0,256,0,256])

kelima untuk melakukan beberapa operasi pemrosesan gambar menggunakan OpenCV (cv2), seperti perubahan ruang warna, perhitungan histogram untuk masing-masing saluran warna (merah, hijau, dan biru), dan perhitungan histogram untuk seluruh gambar dalam ruang warna RGB. 
- color_image = cv2.imread('namasaya.jpg'): Ini membaca gambar 'namasaya.jpg' dari sistem file dan menyimpannya dalam variabel color_image menggunakan OpenCV. Fungsi cv2.imread() digunakan untuk membaca gambar.
- color_image = cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB): Ini mengubah ruang warna gambar dari BGR (Blue-Green-Red) menjadi RGB (Red-Green-Blue), karena OpenCV secara default membaca gambar dalam format BGR, sedangkan matplotlib mengharapkan gambar dalam format RGB.
- histogram_biru = cv2.calcHist([b],[0],None,[256],[0,256]), histogram_hijau = cv2.calcHist([g],[0],None,[256],[0,256]), histogram_merah = cv2.calcHist([r],[0],None,[256],[0,256]): Ini adalah baris kode yang menghitung histogram untuk masing-masing saluran warna (biru, hijau, dan merah) menggunakan fungsi cv2.calcHist(). Histogram adalah representasi distribusi intensitas warna dalam gambar.
- histogram_warna = cv2.calcHist([color_image],[0,1,2],None,[256,256,256],[0,256,0,256,0,256]): Ini menghitung histogram untuk seluruh gambar dalam ruang warna RGB. Kami menggunakan tiga saluran warna (merah, hijau, dan biru) dan membagi masing-masing saluran warna menjadi 256 bin untuk menghitung histogram.

#plt.figure(figsize=(12, 8))

#plt.subplot(2, 2, 1) 
#plt.plot(histogram_biru, color='b')
#plt.title( 'Histogram Biru')
#plt.xlim([0, 256])

#plt.subplot (2, 2, 2)
#plt.plot(histogram_hijau, color='g')
#plt.title( 'Histogram Hijau')
#plt.xlim([0, 256])

#plt.subplot (2, 2, 3) 
#plt.plot(histogram_merah, color='r')
#plt.title( 'Histogram Merah')
#plt.xlim([0, 256])

#plt.subplot (2, 2, 4)
#plt.plot(histogram_warna.flatten(), color='gray')
#plt.title('Histogram Warna')
#plt.xlim([0, 256])

keenam untuk menampilkan histogram masing-masing saluran warna (biru, hijau, dan merah) serta histogram untuk seluruh gambar dalam ruang warna RGB dalam subplot yang terpisah. 
- plt.figure(figsize=(12, 8)): Ini membuat sebuah figure dengan ukuran 12x8 inch menggunakan matplotlib.
- plt.subplot(2, 2, 1), plt.subplot(2, 2, 2), plt.subplot(2, 2, 3), plt.subplot(2, 2, 4): Ini adalah baris kode yang membuat empat subplot di dalam figure. plt.subplot() digunakan untuk menentukan letak dan ukuran subplot dalam grid. Dalam hal ini mempunyai grid 2x2, yang berarti ada empat subplot, dan memberikan nomor subplot yang sesuai untuk setiap histogram.
- plt.plot(histogram_biru, color='b'), plt.plot(histogram_hijau, color='g'), plt.plot(histogram_merah, color='r'), plt.plot(histogram_warna.flatten(), color='gray'): Ini adalah baris kode yang menggambar histogram untuk masing-masing saluran warna (biru, hijau, dan merah) serta histogram untuk seluruh gambar dalam ruang warna RGB. Fungsi plt.plot() digunakan untuk menggambar histogram. Argumen color digunakan untuk menentukan warna garis histogram. Pada histogram untuk seluruh gambar (histogram warna), dan menggunakan .flatten() untuk mengubah matriks 3D menjadi array 1D sebelum menggambar histogramnya.
plt.title(): Ini digunakan untuk memberikan judul pada setiap subplot.
plt.xlim([0, 256]): Ini digunakan untuk menentukan batas sumbu x pada histogram. Rentang intensitas warna adalah 0 hingga 255, jadi untuk membatasi sumbu x dari 0 hingga 256 untuk menampilkan seluruh rentang intensitas warna.

#plt.figure(figsize=(20, 5))

#plt.subplot(141)
#plt.title('Histogram Asli')
#plt.hist(color_image.flatten(), bins=256, range=[0,256], color='gray')

#plt.subplot(142)
#plt.title('Histogram merah')
#plt.hist(r.flatten(), bins=256, range=[0,256], color='r')

#plt.subplot(143)
#plt.title('Histogram hijau')
#plt.hist(g.flatten(), bins=256, range=[0,256], color='g')

#plt.subplot(144)
#plt.title('Histogram biru')
#plt.hist(b.flatten(), bins=256, range=[0,256], color='b')

#plt.show()

ketujuh sama seperti hal nya dengan source code keenam untuk menampilkan histogram untuk masing-masing saluran warna (biru, hijau, dan merah) serta histogram untuk seluruh gambar dalam ruang warna RGB dalam subplot yang terpisah. namun mempunyai beda yaitu 
- plt.figure(figsize=(20, 5)): Ini membuat sebuah figure dengan ukuran 20x5 inch menggunakan matplotlib.
- plt.subplot(141), plt.subplot(142), plt.subplot(143), plt.subplot(144): Ini adalah baris kode yang membuat empat subplot di dalam figure. plt.subplot() digunakan untuk menentukan letak dan ukuran subplot dalam grid. ada grid 1x4, yang berarti ada empat subplot, memberikan nomor subplot yang sesuai untuk setiap histogram.
- plt.hist(): Ini adalah fungsi yang digunakan untuk menggambar histogram. Di sini, kami menggunakan plt.hist() untuk menghitung dan menampilkan histogram. Argumen color digunakan untuk menentukan warna histogram.
- color_image.flatten(), r.flatten(), g.flatten(), b.flatten(): Ini adalah operasi yang digunakan untuk meratakan matriks gambar dan saluran warna merah, hijau, dan biru menjadi array 1D sebelum dihitung histogramnya. Operasi flatten() digunakan untuk mengubah matriks 2D menjadi array 1D.
- bins=256, range=[0,256]: Ini adalah argumen yang digunakan untuk menentukan jumlah bin histogram dan rentang intensitas warna yang ingin ditampilkan. Rentang intensitas warna adalah 0 hingga 255, dan kami menggunakan 256 bin untuk menampilkan seluruh rentang intensitas warna.
- plt.show(): Ini adalah perintah untuk menampilkan plot yang telah dibuat.

#def make_image_invisible(image):
    #height, width = image.shape[:2]
    #return np.zeros((height, width, 3), dtype=np.uint8)
#def increase_brightness(image, value=30):
    #hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
    #h, s, v = cv2.split(hsv)
    #v += value
    #v = np.clip(v, 0, 255)
    #final_hsv = cv2.merge((h, s, v))
    #return cv2.cvtColor(final_hsv, cv2.COLOR_HSV2BGR)
#def detect_and_highlight_blue(image):
    #hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
    #lower_blue = np.array([100, 50, 50])
    #upper_blue = np.array([130, 255, 255])
    #blue_mask = cv2.inRange(hsv, lower_blue, upper_blue)
    
    #result = cv2.bitwise_and(image, image, mask=blue_mask)
    #return result
#def detect_and_highlight_red_blue(image):
    #hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
    #lower_red1 = np.array([0, 50, 50])
    #upper_red1 = np.array([10, 255, 255])
    #red_mask1 = cv2.inRange(hsv, lower_red1, upper_red1)
    #lower_red2 = np.array([170, 50, 50])
    #upper_red2 = np.array([180, 255, 255])
    #red_mask2 = cv2.inRange(hsv, lower_red2, upper_red2)
    #red_mask = cv2.bitwise_or(red_mask1, red_mask2)
    
    #lower_blue = np.array([100, 50, 50])
    #upper_blue = np.array([130, 255, 255])
    #blue_mask = cv2.inRange(hsv, lower_blue, upper_blue)
    
    #combined_mask = cv2.bitwise_or(red_mask, blue_mask)
    #result = cv2.bitwise_and(image, image, mask=combined_mask)
    #return result
#def detect_and_highlight_red_green_blue(image):
    #hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
    #lower_red1 = np.array([0, 50, 50])
    #upper_red1 = np.array([10, 255, 255])
    #red_mask1 = cv2.inRange(hsv, lower_red1, upper_red1)
    #lower_red2 = np.array([170, 50, 50])
    #upper_red2 = np.array([180, 255, 255])
    #red_mask2 = cv2.inRange(hsv, lower_red2, upper_red2)
    #red_mask = cv2.bitwise_or(red_mask1, red_mask2)
    
    #lower_green = np.array([40, 50, 50])
    #upper_green = np.array([200, 255, 255])
    #green_mask = cv2.inRange(hsv, lower_green, upper_green)
    
    #lower_blue = np.array([100, 50, 50])
    #upper_blue = np.array([130, 255, 255])
    #blue_mask = cv2.inRange(hsv, lower_blue, upper_blue)
    
    #combined_mask = cv2.bitwise_or(red_mask, cv2.bitwise_or(green_mask, blue_mask))
    #result = cv2.bitwise_and(image, image, mask=combined_mask)
    #return result

kedelapan memiliki fungsi yang berbeda beda, yaitu untuk memisahkan setiap warna yang berada di citra 
- make_image_invisible(image): Fungsi ini bertujuan untuk membuat gambar menjadi tidak terlihat. Ini dilakukan dengan membuat matriks gambar baru yang berisi semua nol, sehingga gambar tersebut menjadi hitam saat ditampilkan. Fungsi ini berguna untuk beberapa aplikasi di mana kita ingin menyembunyikan gambar tetapi mempertahankan ukurannya.
- increase_brightness(image, value=30): Fungsi ini bertujuan untuk meningkatkan kecerahan gambar. Ini dilakukan dengan mengubah ruang warna gambar ke HSV (Hue-Saturation-Value), menambahkan nilai ke komponen nilai (V) yang mewakili kecerahan, dan kemudian mengembalikan gambar ke ruang warna BGR (Blue-Green-Red).
- detect_and_highlight_blue(image): Fungsi ini bertujuan untuk mendeteksi dan menyoroti bagian-bagian biru dalam gambar. Ini dilakukan dengan mengubah ruang warna gambar ke HSV, menentukan batasan untuk warna biru dalam format HSV, dan kemudian menerapkan masker untuk menyoroti bagian-bagian yang sesuai dengan warna biru.
- detect_and_highlight_red_blue(image): Fungsi ini bertujuan untuk mendeteksi dan menyoroti bagian-bagian merah dan biru dalam gambar. Ini dilakukan dengan mengubah ruang warna gambar ke HSV, menentukan batasan untuk warna merah dan biru dalam format HSV, dan kemudian menerapkan masker untuk menyoroti bagian-bagian yang sesuai dengan warna merah dan biru.
- detect_and_highlight_red_green_blue(image): Fungsi ini bertujuan untuk mendeteksi dan menyoroti bagian-bagian merah, hijau, dan biru dalam gambar. Ini dilakukan dengan mengubah ruang warna gambar ke HSV, menentukan batasan untuk warna merah, hijau, dan biru dalam format HSV, dan kemudian menerapkan masker untuk menyoroti bagian-bagian yang sesuai dengan warna merah, hijau, dan biru.

#image = cv2.imread('namasaya.jpg')
#invisible_image = make_image_invisible(image)
#brightened_image = increase_brightness(image)
#blue_detection = detect_and_highlight_blue(brightened_image)
#red_blue_detection = detect_and_highlight_red_blue(brightened_image)
#red_green_blue_detection = detect_and_highlight_red_green_blue(brightened_image)

#plt.figure(figsize=(10, 8))

#plt.subplot(221), plt.imshow(cv2.cvtColor(invisible_image, cv2.COLOR_BGR2RGB)), plt.title('None')
#plt.subplot(222), plt.imshow(cv2.cvtColor(blue_detection, cv2.COLOR_BGR2RGB)), plt.title('Blue Color Detection')
#plt.subplot(223), plt.imshow(cv2.cvtColor(red_blue_detection, cv2.COLOR_BGR2RGB)), plt.title('Red-Blue Color Detection')
#plt.subplot(224), plt.imshow(cv2.cvtColor(red_green_blue_detection, cv2.COLOR_BGR2RGB)), plt.title('Red-Green-Blue Color Detection')

#plt.show()

Kode di atas membaca gambar dari file 'namasaya.jpg' menggunakan OpenCV, kemudian melakukan beberapa operasi pemrosesan gambar dengan fungsi-fungsi yang telah Anda definisikan sebelumnya, dan akhirnya menampilkan hasilnya dalam sebuah plot.
- image = cv2.imread('namasaya.jpg'): Ini membaca gambar 'namasaya.jpg' dari sistem file menggunakan OpenCV.
- invisible_image = make_image_invisible(image): Ini menggunakan fungsi make_image_invisible() yang telah Anda definisikan sebelumnya untuk membuat gambar tidak terlihat (dalam hal ini, menjadi hitam).
- brightened_image = increase_brightness(image): Ini menggunakan fungsi increase_brightness() untuk meningkatkan kecerahan gambar.
- blue_detection = detect_and_highlight_blue(brightened_image): Ini menggunakan fungsi detect_and_highlight_blue() untuk mendeteksi dan menyoroti bagian-bagian biru dalam gambar yang telah ditingkatkan kecerahannya.
- red_blue_detection = detect_and_highlight_red_blue(brightened_image): Ini menggunakan fungsi detect_and_highlight_red_blue() untuk mendeteksi dan menyoroti bagian-bagian merah dan biru dalam gambar yang telah ditingkatkan kecerahannya.
- red_green_blue_detection = detect_and_highlight_red_green_blue(brightened_image): Ini menggunakan fungsi detect_and_highlight_red_green_blue() untuk mendeteksi dan menyoroti bagian-bagian merah, hijau, dan biru dalam gambar yang telah ditingkatkan kecerahannya.
- plt.figure(figsize=(10, 8)): Ini membuat sebuah figure dengan ukuran 10x8 inch menggunakan matplotlib.
- plt.subplot(): Ini adalah baris kode yang membuat subplot di dalam figure dan menampilkan setiap gambar yang telah diproses dalam subplot yang sesuai.
- plt.imshow(cv2.cvtColor(), cv2.COLOR_BGR2RGB): Ini adalah baris kode yang menampilkan gambar dalam subplot. Kita menggunakan cv2.cvtColor() untuk mengonversi gambar dari format BGR ke RGB karena matplotlib menggunakan format RGB.
- plt.title(): Ini digunakan untuk memberikan judul pada setiap subplot.
- plt.show(): Ini adalah perintah untuk menampilkan plot yang telah dibuat.

Berikut adalah beberapa teori yang mendukung project ini:

- Pemrosesan Gambar dengan OpenCV: OpenCV adalah pustaka populer untuk pemrosesan gambar dan video. Dalam codingan tersebut, kita menggunakan fungsi-fungsi OpenCV seperti cv2.imread() untuk membaca gambar, cv2.cvtColor() untuk mengubah ruang warna gambar, cv2.split() dan cv2.merge() untuk memisahkan dan menggabungkan saluran warna, dan cv2.bitwise_and() untuk menerapkan operasi bitwise pada gambar.
- Manipulasi Array dengan NumPy: NumPy adalah pustaka Python yang kuat untuk komputasi numerik, terutama dalam manipulasi array dan matriks. Dalam codingan tersebut, kita menggunakan NumPy untuk melakukan operasi pada matriks gambar, seperti slicing, meratakan matriks, dan melakukan operasi aritmatika elemen-wise.
- Representasi Ruang Warna: Ruang warna adalah cara untuk merepresentasikan warna dalam sebuah gambar. Dalam codingan tersebut, kita menggunakan ruang warna HSV (Hue-Saturation-Value) untuk beberapa operasi deteksi warna. Ruang warna HSV memisahkan komponen warna (hue), kecerahan (value), dan saturasi (saturation), yang memudahkan deteksi warna terlepas dari variasi kecerahan.
- Histogram: Histogram adalah representasi distribusi intensitas warna dalam sebuah gambar. Dalam codingan tersebut, kita menggunakan histogram untuk menganalisis distribusi intensitas warna dalam gambar, baik secara keseluruhan maupun untuk masing-masing saluran warna.
- Visualisasi dengan Matplotlib: Matplotlib adalah pustaka Python yang digunakan untuk membuat visualisasi data, termasuk plot gambar dan histogram. Dalam codingan tersebut, kita menggunakan Matplotlib untuk menampilkan gambar dan histogram dalam subplot.






