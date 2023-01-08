# SIG_TEORI_TGS11
 georeferencing topo sheets and scanned maps
 
 # Langkah kerja

1. Buka QGIS dan klik Raster ‣ Georeferencer untuk membuka alat.

2. Georeferensi dibagi menjadi 2 bagian. Bagian atas tempat gambar akan ditampilkan dan bagian bawah tempat tabel yang menunjukkan GCP Anda akan muncul.

3. Sekarang kita akan membuka gambar JPG kita. Buka File ‣ Buka Raster . Telusuri ke gambar yang diunduh dari peta yang dipindai dan klik Buka .

4. Anda akan melihat gambar akan dimuat di bagian atas. Anda dapat menggunakan kontrol zoom/pan pada bilah alat untuk mempelajari lebih lanjut tentang peta.

5. Sekarang kita perlu menetapkan koordinat ke beberapa titik di peta ini. Jika Anda melihat lebih dekat, Anda akan melihat kotak koordinat dengan tanda. Ini adalah garis grid Lintang dan Bujur.

6. Sebelum menambahkan Titik Kontrol Tanah (GCP), kita perlu menentukan Pengaturan Transformasi. Klik ikon roda gigi di jendela georeferensi untuk membuka dialog pengaturan Transformasi.

7. Dalam dialog Pengaturan transformasi , pilih jenis Transformasi sebagai . Lihat Dokumentasi QGIS untuk mempelajari tentang berbagai jenis transformasi dan penggunaannya. Kemudian pilih metode Resampling sebagai . Klik tombol Select CRS di sebelah Target SRS .Polynomial 2Nearest neighbor

8. Jika Anda melakukan geo-referensi peta yang dipindai seperti ini, Anda dapat memperoleh informasi CRS dari peta itu sendiri. Melihat gambar peta kita, koordinatnya ada di Lintang/Bujur. Tidak ada informasi datum yang diberikan, jadi kita harus mengasumsikan yang sesuai. Karena ini adalah India dan petanya cukup tua, kita bisa bertaruh bahwa data Everest 1830 akan memberi kita hasil yang baik. Cari everestdan pilih CRS dengan definisi terlama dari datum Everest (EPSG:4042). Klik Oke .

9. Beri nama raster keluaran Anda sebagai 1870_southern_india_modified.tif. Pilih LZWsebagai Kompresi . Periksa Simpan poin GCP untuk menyimpan poin sebagai file terpisah untuk tujuan di masa mendatang. Pastikan opsi Muat di QGIS saat selesai dicentang. Klik Oke .

10. Sekarang kita dapat mulai menambahkan Ground Control Points (GCP). Klik pada tombol Tambah Titik .

11. Sekarang tempatkan cross-hair di persimpangan garis grid dan klik kiri, ini akan berfungsi sebagai ground-truth dalam kasus kita. Saat garis kisi diberi label, kita dapat menentukan koordinat X dan Y dari titik-titik tersebut. Di jendela pop-up, masukkan koordinat. Ingat bahwa X = bujur dan Y = lintang. Klik Oke .

12. Anda akan melihat tabel GCP sekarang memiliki baris dengan detail GCP pertama Anda.

13. Demikian pula, tambahkan lebih banyak GCP yang mencakup seluruh gambar. Semakin banyak poin yang Anda miliki, semakin akurat gambar Anda didaftarkan ke koordinat target. Transformasi membutuhkan setidaknya 6 GCP. Setelah Anda menambahkan jumlah poin minimum yang diperlukan untuk transformasi, Anda akan melihat bahwa GCP sekarang memiliki nilai bukan nol dan kesalahan . Jika GCP tertentu memiliki nilai error yang luar biasa tinggi, hal itu biasanya berarti kesalahan manusia dalam memasukkan nilai koordinat. Jadi, Anda dapat menghapus GCP itu dan menangkapnya lagi. Anda juga dapat mengedit nilai koordinat di Tabel GCP dengan mengeklik sel di salah satu Tujuan. X atau Des. kolom Y.Polynomial 2dXdYResidual

14. Setelah Anda puas dengan GCP, klik tombol Mulai Georeferensi . Ini akan memulai proses membengkokkan gambar menggunakan GCP dan membuat raster target.

15. Setelah proses selesai, Anda akan melihat lapisan georeferensi dimuat di QGIS. Georeferensi sekarang selesai. Juga, Anda akan melihat Project CRS di kanan bawah diatur ke EPSG:4042 seperti yang dijelaskan di Pengaturan Transformasi.

16. Seret dan lepas OpenStreetMapas Base Map dari dropdown XYZ Tiles di bagian bawah panel Browser untuk memverifikasi lapisan georeferensi. Untuk menyetel transparansi, klik ikon Open layer styling panel dan pilih tab Transparency . Atur transparansi menjadi . Sekarang gambar georeferensi harus dilapisi dengan garis peta dasar.40 %

17. Jika georeferensi membutuhkan lebih banyak penyesuaian, kita dapat mulai dari poin GCP yang terkumpul. Telusuri 1870_southern_india_modified.tiflokasi file. Anda dapat menemukan file tambahan, 1870_southern_india_modified.tif.points. File ini akan berisi informasi poin GCP.

18. Buka alat georeferensi di QGIS, klik File ‣ Load GCP Points , dan pilih 1870_southern_india_modified.tif.points. Ini akan memuat GCP yang dibuat sebelumnya. Kemudian muat 1870_southern_india_modified.tifuntuk menyempurnakan pekerjaan Anda.
