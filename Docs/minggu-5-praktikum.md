# Praktikum Minggu 5 — CRUD

## Endpoint
Daftar alamat yang dipakai di Postman:

| Method | Alamat | Kegunaan |
|---|---|---|
| GET | /api/books | Menampilkan semua buku |
| POST | /api/books | Menambah buku baru |
| GET | /api/books/{nomor} | Menampilkan satu buku saja |
| PATCH | /api/books/{nomor} | Mengubah data buku |
| DELETE | /api/books/{nomor} | Menghapus buku |

## Aturan Validasi

### Saat Menambah Buku
- `title` — Wajib diisi, tidak boleh kosong, panjang 3 sampai 200 huruf
- `isbn` — Wajib diisi, harus 13 angka, belum dipakai buku lain
- `available` — Boleh diisi boleh tidak, isinya cuma benar atau salah

### Saat Mengubah Buku
- Kalau tidak dikirim, datanya tetap seperti semula
- Kalau dikirim, baru dicek sesuai aturan di atas
- Khusus ISBN: kalau tidak diubah, sistem tidak menganggapnya sama dengan buku lain

## Hasil Pengecekan

| Kode | Keterangan | Apakah Berhasil? |
|---|---|---|
| 201 | Buku berhasil dibuat |  Muncul data buku yang baru |
| 422 | Data salah atau kurang |  Muncul tulisan mana yang kurang |
| 200 | Data berhasil diubah | Yang diubah berubah, yang lain tetap |
| 404 | Buku tidak ada | Muncul tulisan "Book not found" |
| 204 | Buku berhasil dihapus | Tidak ada tulisan apa-apa di bagian bawah |

## Perbandingan Hasil
Saya sudah mencoba semua tes di Postman dan hasilnya sama seperti yang diharapkan. Tidak ada yang berbeda.

## Penggunaan Bantuan/AI Usage
Saya memakai bantuan untuk:
- Memahami cara kerja alur dari kirim data sampai masuk ke database
- Menyusun kode supaya tidak salah tulis
- Mencari tahu kenapa muncul pesan error dan cara memperbaikinya
- Menyusun catatan ini supaya rapi

## Cara memeriksa hasilnya:
- Cek satu per satu di Postman, apakah kode yang muncul sudah benar
- Pastikan nomor ID di alamat sudah diganti dengan nomor buku yang sebenarnya
- Cek sebelum mengirim ke Git, tidak ada data rahasia yang ikut terkirim