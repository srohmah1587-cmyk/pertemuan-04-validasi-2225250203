# Pertemuan 04 – Seleksi Multi-Kondisi dan Validasi Input

**Nama:** Siti Rohmah
**NIM:** 2225250203
**Kelas:** 3A

## Tujuan

Membangun program validasi dan klasifikasi nilai menggunakan struktur seleksi multi-kondisi dengan rantai `if-elif-else`. Program dibuat untuk mengelompokkan nilai berdasarkan kategori tertentu serta melakukan validasi terhadap input yang diberikan oleh pengguna.

## Cara Menjalankan

Program dapat dijalankan menggunakan perintah berikut:

```bash
python3 praktik/validasi_klasifikasi_nilai.py
```

Pastikan Python sudah terpasang pada komputer dan file program berada pada lokasi yang sesuai.

## Tabel Keputusan

| Kategori          | Syarat               | Contoh Masukan |
| ----------------- | -------------------- | -------------: |
| Nilai A           | Nilai 85–100         |             90 |
| Nilai B           | Nilai 75–84          |             80 |
| Nilai C           | Nilai 65–74          |             70 |
| Nilai D           | Nilai 50–64          |             60 |
| Nilai E           | Nilai 0–49           |             40 |
| Input tidak valid | Nilai kurang dari 0  |             -5 |
| Input tidak valid | Nilai lebih dari 100 |            105 |
| Input tidak valid | Masukan bukan angka  |          `abc` |

## Hasil Pengujian

| No. | Masukan | Keluaran yang Diharapkan | Keluaran Aktual   | Status   |
| --: | ------- | ------------------------ | ----------------- | -------- |
|   1 | 90      | Kategori A               | Kategori A        | Berhasil |
|   2 | 80      | Kategori B               | Kategori B        | Berhasil |
|   3 | 70      | Kategori C               | Kategori C        | Berhasil |
|   4 | 60      | Kategori D               | Kategori D        | Berhasil |
|   5 | 40      | Kategori E               | Kategori E        | Berhasil |
|   6 | 105     | Input tidak valid        | Input tidak valid | Berhasil |
|   7 | -5      | Input tidak valid        | Input tidak valid | Berhasil |
|   8 | `abc`   | Input tidak valid        | Input tidak valid | Berhasil |

## Contoh Program

```python
# Program Validasi dan Klasifikasi Nilai

try:
    nilai = float(input("Masukkan nilai (0-100): "))

    if nilai < 0 or nilai > 100:
        print("Input tidak valid. Nilai harus berada pada rentang 0-100.")
    elif nilai >= 85:
        print("Kategori A")
    elif nilai >= 75:
        print("Kategori B")
    elif nilai >= 65:
        print("Kategori C")
    elif nilai >= 50:
        print("Kategori D")
    else:
        print("Kategori E")

except ValueError:
    print("Input tidak valid. Masukkan angka.")

    if hadir < 80:
        print("Kehadiran tidak memenuhi syarat minimal 80%")
        print("Status kehadiran: Belum Lulus")
    else:
        print("Status kehadiran: Lulus")

        if akhir >= 85:
            predikat = "A"
        elif akhir >= 70:
            predikat = "B"
        elif akhir >= 60:
            predikat = "C"
        elif akhir >= 50:
            predikat = "D"
        else:
            predikat = "E"
            print(f"Predikat = {predikat}")
        if predikat in ["A", "B", "C"]:
            status = "Lulus"
        else:
            status = "Belum Lulus"
    print("Predikat:", predikat)
    print("Status:", status)
```

## Refleksi

Salah satu masukan tidak valid yang semula terlewat adalah nilai yang berada di luar rentang 0–100, misalnya nilai `105`. Jika program hanya menggunakan kondisi `if-elif-else` untuk mengelompokkan nilai tanpa melakukan validasi terlebih dahulu, nilai tersebut dapat dikategorikan secara tidak tepat.

Untuk menangani masalah tersebut, ditambahkan validasi input dengan memeriksa apakah nilai berada dalam rentang 0 sampai 100. Jika nilai kurang dari 0 atau lebih dari 100, program akan menampilkan pesan bahwa input tidak valid.

Selain itu, masukan yang bukan berupa angka, seperti `abc`, juga perlu ditangani. Hal tersebut dilakukan menggunakan `try-except` dengan `ValueError` sehingga program tidak berhenti karena kesalahan input.

Dengan adanya validasi tersebut, program menjadi lebih aman dan mampu menangani berbagai kemungkinan masukan dari pengguna sebelum melakukan proses klasifikasi nilai.
