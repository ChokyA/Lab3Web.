# Lab3Web.
# MEMBUAT APLIKASI CRUD SEDERHANA
Untuk dapat membuat aplikasi CRUD ini, ada beberapa hal yang harus disiapkan. Pertama, karena disini menggunaka MySQL sebagai database servernya pastikanlah MySQL kalian sudah dapat dijalankan melalui Xampp seperti gambar dibawah.
![Screenshot (121)](https://user-images.githubusercontent.com/93463612/227775352-5db4000e-7fe3-40fe-ab60-ac983485d650.png)

# PEMBUATAN DATABASE
langsung saja kita membuat database pada PHPMyAdmin dengan mengklik tombol MySQL yang ada diatas kemudian masukan kode dibawah kemudian klik kirim.

CREATE DATABASE Latihan1;

# PEMBUATAN TABEL

![Screenshot (128)](https://user-images.githubusercontent.com/93463612/227775764-1aceca46-c3fa-4092-9916-c3f022e9432c.png)



Setelah database berhasil dibuat. Selanjutnya proses pembuatan tabel pada database tersebut. Pembuatannya sama dengan sebelumnya, kalian hanya perlu menekan tombol MySQL pada Database sebelumnya kemudian masukan kode berikut:

CREATE TABLE data_barang (
        id_barang int(10) auto_increment Primary Key,
        kategori varchar(30),
        nama varchar(30),
        gambar varchar(100),
        harga_beli decimal(10,0),
        harga_jual decimal(10,0),
        stok int(4)
);

PENAMBAHAN DATA

![Screenshot (129)](https://user-images.githubusercontent.com/93463612/227775782-3dc53056-cb5f-472e-8faa-a3501a36bb31.png)


Untuk dapat menambahkan data pada tabel yang sudah dibuat sebelumnya, kalian hanya perlu memasukan kode berikut pada bagian MySQLnya:

INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES ('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);

PEMBUATAN PROGRAM CRUD
Pertama, buatlah sebuah folder baru dengan nama lab3_php_database pada root directory web server (C:\xampp\htdocs\lab3web)

# MEMBUAT FILE KONEKSI DATABASE
Buatlah file baru dalam Directory Lab3_php_dasar dengan nama file koneksi.php kemuadian masukan kode berikut:

<?php
$host = "localhost:3307";
$user = "root";
$pass = "";
$db = "latihan1";

$conn = mysqli_connect($host, $user, $pass, $db);
if ($conn == false)
{
    echo "Koneksi ke server gagal.";
    die();
} else echo "Koneksi berhasil";
?>

jika koneksi berhasil maka anda akan mendapatkan hasil seperti gambar dibawah ini.

![Screenshot (130)](https://user-images.githubusercontent.com/93463612/227775913-b27b76a9-5523-416d-92a6-9c6b672903c3.png)


MENAMPILKAN DATA DENGAN FILE INDEX (READ)

![Screenshot (134)](https://user-images.githubusercontent.com/93463612/227775952-3a462323-b69e-41a6-8807-86a59eecbe06.png)


MENAMBAHKAN DATA (CREATE)
Kita dapat menambahkan data agar muncul pada tabel, maka tampilannya akan seperti berikut.

![Screenshot (138)](https://user-images.githubusercontent.com/93463612/227775979-ebaf4f3a-cfc4-48ae-86fb-63e08c176bc4.png)


MENGUBAH DATA (UPDATE)
kita dapat mengubah data yang berada di dalam tabel, contohnya seperti pada gambar dibawah ini

![Screenshot (140)](https://user-images.githubusercontent.com/93463612/227776050-a78e1d51-571b-4958-9d1d-0c0eb71b3728.png)

MENGHAPUS DATA (DELETE)
Jika ingin menghapus sebuah data yang ada, kita hanya perlu mengklik kolom Hapus pada index table yang nantinya akan secara otomatis data tersebut akan terhapus oleh program.

![Screenshot (141)](https://user-images.githubusercontent.com/93463612/227776150-3e78d9fc-9e92-4147-b418-a8cb36591755.png)


