# eksperimen

awalnya kita membuat databasenya terlebih dahulu

```
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50),
  email VARCHAR(100)
);
```

selanjutnya kita membuat tabel di databasenya
contoh :

```
INSERT INTO users (username, email) VALUES ('kii', 'kii@areone.com');
INSERT INTO users (username, email) VALUES ('itoo', 'itoo@areone.com');
```

lalu aku buat website kecil pakai PHP dan MySQL untuk coba-coba. Contohnya kayak gini:
![● index php - uas - Visual Studio Code 01_05_2025 23_57_03](https://github.com/user-attachments/assets/b00990e7-9d45-4c7c-a328-f81d1b8cb2f1)

kalau sudah kita akses urlnya seperti ini

```
http://localhost/namafolder/index.php?id=1
```
hasilnya

![localhost_uas_index php_id=1 - Google Chrome 02_05_2025 17_53_45](https://github.com/user-attachments/assets/32144368-8eb6-4597-b085-7e1cec3bec00)

maka akan tampil data pengguna ID = 1

Tapi kalau diubah jadi:
```
http://localhost/namafolder/index.php?id=1' OR '1'='1
```

![localhost_uas_index php_id=1%27 OR %271%27=%271 - Google Chrome 02_05_2025 18_01_25](https://github.com/user-attachments/assets/95fa27cc-9292-478e-b704-64b6acac0913)

tiba-tiba semua data pengguna muncul! Ini bahaya banget, kan? Website itu rentan banget kalau nggak diproteksi.

nah sekarang saatnya kita amanin webbsitenya menggunakan prepared statements kaya gini

![index php - uas - Visual Studio Code 02_05_2025 00_06_08](https://github.com/user-attachments/assets/20d1f278-6b3f-4d6e-a596-dd23ba90a2ac)

kalo kita cek lagi menggunakan
```
http://localhost/namafolder/index.php?id=1' OR '1'='1
```
![localhost_uas_index php_id=1%27 OR %271%27=%271 - Google Chrome 02_05_2025 18_07_38](https://github.com/user-attachments/assets/5ccf76ed-b616-49e7-8aaa-95c6795a3795)

Nah, dengan cara ini, input dari pengguna dianggap sebagai data, bukan bagian dari query SQL. Jadi, serangan kayak tadi nggak bakal berhasil lagi!


