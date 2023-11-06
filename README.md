# UTS-database
## ACID
ACID adalah singkatan dari Atomicity, Consistency, Isolation, dan Durability. Keempat karakteristik ini adalah prinsip-prinsip yang digunakan dalam database untuk memastikan bahwa transaksi yang dilakukan pada database adalah aman dan dapat diandalkan. Berikut adalah penjelasan singkat dari keempat karakteristik ACID:
- Atomicity: Transaksi harus dianggap sebagai satu unit tunggal yang tidak dapat dibagi-bagi. Jika ada kesalahan dalam transaksi, maka seluruh transaksi harus dibatalkan.
- Consistency: Setiap transaksi harus memastikan bahwa database berada dalam keadaan yang konsisten sebelum dan sesudah transaksi dilakukan.
- Isolation: Setiap transaksi harus diisolasi dari transaksi lain yang sedang berlangsung pada waktu yang sama. Hal ini memastikan bahwa transaksi tidak saling mengganggu satu sama lain.
- Durability: Setiap transaksi yang telah selesai harus tetap ada dan tidak dapat dihapus dari database. Hal ini memastikan bahwa data yang telah dimasukkan ke dalam database tetap aman dan dapat diandalkan.

## REFERENTIAL INTEGRITY CONSTRAINT
Foreign key (kunci asing) adalah kolom atau sekelompok kolom dalam sebuah tabel yang merujuk ke primary key atau unique key di tabel lain. Foreign key memiliki peran penting dalam implementasi referential integrity (integritas referensial) dalam sebuah basis data. Referential integrity adalah prinsip yang memastikan bahwa hubungan antara tabel dalam basis data tetap konsisten dan valid. Berikut adalah peran utama foreign key dalam implementasi referential integrity:
1. Menentukan Hubungan Antara Tabel:
   - Foreign key digunakan untuk menentukan hubungan atau asosiasi antara dua tabel dalam basis data.
2. Mencegah Data yang Tidak Valid:
   - Dengan adanya foreign key constraints, basis data dapat memastikan bahwa hanya data yang sah dan konsisten yang dimasukkan ke dalam tabel.
3. Memastikan Integritas Referensial:
   - Integritas referensial adalah prinsip yang memastikan bahwa setiap nilai dalam kolom foreign key ada dalam kolom yang sesuai dalam tabel referensi (tabel yang diacu).
4. Melakukan Aksi Terkait:
   - Foreign key juga dapat dikonfigurasi untuk menjalankan aksi tertentu saat terjadi perubahan pada data terkait. Contoh tindakan ini termasuk
     - RESTRICT (mencegah penghapusan data yang masih digunakan oleh foreign key),
     - CASCADE (menghapus atau memperbarui data terkait saat data referensi diubah),
     - SET NULL (mengatur nilai foreign key menjadi NULL saat data referensi dihapus), dan
     - NO ACTION (mencegah aksi yang melanggar integritas referensial).
Dengan menggunakan foreign key, Anda dapat membangun dan mempertahankan hubungan yang konsisten dan valid antara tabel dalam basis data, menjaga integritas referensial, dan mencegah data yang tidak sah masuk ke dalam database. Ini sangat penting untuk memastikan bahwa data dalam database tetap konsisten dan dapat diandalkan.

## Jenis-jenis dependency
Dependensi fungsional adalah hubungan antara atribut dalam sebuah tabel di mana nilai dari satu atau beberapa atribut dapat digunakan untuk menentukan nilai atribut lainnya. Dependensi fungsional dapat dibagi menjadi beberapa tipe, termasuk:
- Dependensi Fungsional (Functional Dependency): terjadi ketika nilai satu atribut bergantung pada nilai atribut lainnya.
- Dependensi Fungsional Parsial (Partial Functional Dependency): terjadi ketika suatu atribut bergantung pada atribut lainnya, tetapi tidak sepenuhnya bergantung pada semua nilai atribut tersebut.
- Dependensi Fungsional Transitiv (Transitive Functional Dependency): terjadi ketika atribut A bergantung pada atribut B, yang pada gilirannya bergantung pada atribut C.
- Dependensi Fungsional Reflektif (Trivial Functional Dependency): terjadi ketika sebuah atribut bergantung pada dirinya sendiri.
- Dependensi Fungsional Augmentative (Augmented Functional Dependency): terjadi ketika atribut A bergantung pada kombinasi atribut lain (B dan C).

## Normalisasi
Normalisasi adalah proses desain basis data yang bertujuan untuk mengurangi redundansi data, meningkatkan integritas data, dan mengoptimalkan struktur basis data. Dengan mengikuti prinsip normalisasi, Anda dapat mencapai beberapa manfaat utama yang membantu dalam pengelolaan data yang lebih efisien:
- Mengurangi Redundansi Data: Normalisasi membantu menghindari duplikasi terhadap tabel dalam basis data sehingga tidak ada data redudancy. Hal ini mengurangi pemborosan space hardisk.
- Meningkatkan Integritas Data: Normalisasi membantu memastikan bahwa data yang dimasukkan ke dalam basis data memiliki integritas yang baik dan tidak terjadi anomali data seperti insertion anomalies, deletion anomalies, dan update anomalies.
- Mencegah Anomali Data: Normalisasi membantu menghindari anomali data dengan memastikan bahwa setiap tabel dalam basis data memenuhi kriteria normal form, seperti First Normal Form (1NF), Second Normal Form (2NF), Third Normal Form (3NF), dan Boyce-Codd Normal Form (BCNF).
- Mengoptimalkan Kinerja: Normalisasi membantu mengoptimalkan kinerja basis data dengan mengurangi redundansi data dan memperbaiki struktur basis data.
- Memfasilitasi Perubahan dan Pemeliharaan: Normalisasi membantu memfasilitasi perubahan dan pemeliharaan basis data dengan memperbaiki struktur basis data dan memastikan bahwa setiap tabel dalam basis data memenuhi kriteria normal form.
Tingkat normalisasi yang diterapkan harus seimbang dengan kebutuhan aplikasi dan performa, sehingga tidak selalu diperlukan untuk mencapai tingkat normalisasi tertinggi (e.g., NF-5 atau BCNF) dalam setiap kasus. Tingkat normalisasi yang umum digunakan adalah:
1NF : tidak ada pengulangan data dalam kolom atribut tabel
2NF : Setelah normalisasi ke 1NF, pisah table 1NF dengan aturan tidak ada atribut partial dependency dalam satu tabel
3NF : Setelah normalisasi ke 2NF, pisah table 2NF dengan aturan tidak ada atribut transitive dependency dalam satu tabel
