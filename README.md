# praktikum5.
# praktikum-5

## program sederhana yang akan menampilkan daftar nilai mahasiswa

## flowchart
```
                     ┌─────────────────────────┐
                     │        MULAI            │
                     └───────────────┬─────────┘
                                     │
                                     ▼
                         ┌─────────────────────────┐
                         │ Inisialisasi data = {}  │
                         └───────────────┬─────────┘
                                         │
                                         ▼
                         ┌────────────────────────────────┐
                         │      Tampilkan Menu:           │
                         │ 1. Tambah Data                 │
                         │ 2. Ubah Data                   │
                         │ 3. Hapus Data                  │
                         │ 4. Tampilkan Data              │
                         │ 5. Cari Data                   │
                         │ 0. Keluar                      │
                         └───────────────┬────────────────┘
                                         │
                                         ▼
                         ┌───────────────────────────┐
                         │    Input pilihan menu     │
                         └───────────────┬───────────┘
                                         │
     ┌───────────────────────────────────┼─────────────────────────────────────┐
     │                                   │                                     │
     ▼                                   ▼                                     ▼
 ┌──────────────┐                ┌────────────────┐                     ┌──────────────────┐
 │ Pilihan = 1? │─Yes──────────▶ │  TAMBAH DATA   │                     │ Pilihan = 2?     │
 └───────┬──────┘                └───┬────────────┘                     └───────┬──────────┘
         │                           │                                          │
         │                           ▼                                          ▼
         │                  ┌───────────────────┐                     ┌───────────────────┐
         │                  │ Input NIM         │                     │     UBAH DATA     │
         │                  │ Input Nama        │                     └───────┬───────────┘
         │                  │ Input Tugas       │                             │
         │                  │ Input UTS         │                             ▼
         │                  │ Input UAS         │                 ┌────────────────────────┐
         │                  │ Hitung NilaiAkhir │                 │ Input NIM              │
         │                  │ Simpan ke dict    │                 │ Jika ketemu → ubah     │
         │                  └───────────────────┘                 │ Jika tidak → error     │
         │                            │                           └────────────────────────┘
         │                            ▼                                     │
         │                  ┌────────────────┐                              │
         │                  │ Kembali ke menu│◀─────────────────────────────┘
         │                  └────────────────┘
         │
         │
         ▼
┌──────────────┐
│ Pilihan = 3? │─────────Yes───────────────▶ HAPUS DATA
└───────┬──────┘                              │
        │                                     ▼
        │                          ┌────────────────────────┐
        │                          │ Input NIM              │
        │                          │ Jika ketemu → hapus    │
        │                          │ Jika tidak → error     │
        │                          └────────────────────────┘
        │                                      │
        │                                      ▼
        │                               Kembali ke menu
        │
        ▼
┌──────────────┐
│ Pilihan = 4? │─────────Yes──────────────▶ TAMPILKAN DATA
└───────┬──────┘                             │
        │                                    ▼
        │                        ┌──────────────────────────┐
        │                        │ Cetak seluruh isi dict   │
        │                        │ Jika kosong → tampilkan  │
        │                        │ pesan "tidak ada data"   │
        │                        └──────────────────────────┘
        │                                     │
        │                                     ▼
        │                             Kembali ke menu
        │
        ▼
┌──────────────┐
│ Pilihan = 5? │─────────Yes──────────────▶ CARI DATA
└───────┬──────┘                             │
        │                                    ▼
        │                        ┌──────────────────────────┐
        │                        │ Input NIM                │
        │                        │ Jika ketemu → tampilkan  │
        │                        │ Jika tidak → error       │
        │                        └──────────────────────────┘
        │                                     │
        │                                     ▼
        │                             Kembali ke menu
        │
        ▼
┌──────────────┐
│ Pilihan = 0? │─────────Yes──────────────▶ SELESAI
└───────┬──────┘
        │
        ▼
┌──────────────────────────┐
│   Tampilkan "Salah!"     │
│   Kembali ke menu        │
└──────────────────────────┘

```
## Penjelasan
```
1.  Mulai Program
Program dimulai dan melakukan inisialisasi dictionary kosong:
data = {}
Dictionary ini akan menyimpan semua data mahasiswa dengan format:
data[nim] = {
    "nama": "...",
    "tugas": ...,
    "uts": ...,
    "uas": ...,
    "akhir": ...
}

2. Tampilkan Menu
Program akan menampilkan pilihan:
Tambah Data
Ubah Data
Hapus Data
Tampilkan Data
Cari Data
Keluar
Pengguna harus memilih salah satu nomor.

3. Input Pilihan Menu
User memasukkan angka menu.
Program kemudian mengecek pilihan tersebut:

4. Jika Pilihan = 1 → Tambah Data
Pada menu ini program:
Meminta input:
NIM
Nama
Nilai Tugas
Nilai UTS
Nilai UAS
Menghitung nilai akhir:
akhir = tugas*0.30 + uts*0.35 + uas*0.35
Menyimpan data ke dalam dictionary.
Setelah selesai → kembali ke menu.

5. Jika Pilihan = 2 → Ubah Data
Pada menu ini:
User memasukkan NIM
Program mengecek apakah NIM ada dalam dictionary
Jika ADA → user diminta memasukkan data baru (nama, tugas, uts, uas)
Nilai akhir dihitung ulang
Data diperbarui
Tampilkan pesan sukses
Kembali ke menu
Jika TIDAK ADA → tampilkan pesan error
“Data tidak ditemukan”

6. Jika Pilihan = 3 → Hapus Data
Alurnya:
User memasukkan NIM
Program mencari NIM di dictionary
Jika ADA → data dihapus
Jika TIDAK ADA → tampilkan pesan error

7. Jika Pilihan = 4 → Tampilkan Semua Data
Program akan:
Mengecek apakah dictionary kosong
Jika kosong → tampilkan pesan: “Tidak ada data!”
Jika ada → tampilkan seluruh daftar mahasiswa
Lalu kembali ke menu.

8. Jika Pilihan = 5 → Cari Data
Alur:
User memasukkan NIM
Program mencari NIM tersebut
Jika ADA → tampilkan detail mahasiswa
Jika TIDAK ADA → tampilkan pesan error
Kembali ke menu.

9. Jika Pilihan = 0 → Keluar Program
Program berhenti dan menampilkan pesan:
Program selesai.

10. Jika Input Tidak Valid
Jika user memasukkan angka selain 0–5:
Tampilkan pesan “Menu tidak valid!”
Kembali ke menu utama
```
## kode pemerograman (data_mahasiswa.py)
```python
# Dictionary utama untuk menyimpan data mahasiswa.
# Key akan berupa Nama Mahasiswa, dan Value-nya adalah dictionary detail.
DATA_MAHASISWA = {}


def hitung_nilai_akhir(tugas, uts, uas):
    """Menghitung Nilai Akhir berdasarkan persentase yang ditentukan."""
    # (Tugas: 30%) + (UTS: 35%) + (UAS: 35%)
    nilai_akhir = (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)
    return nilai_akhir


def tampilkan_data():
    """Menampilkan semua data mahasiswa yang tersimpan."""
    print("\n" + "=" * 58)
    print(
        "| NO |   NIM   |      NAMA      | TUGAS |  UTS  |  UAS  | AKHIR |")  # Tampilan sesuai modul [cite: 146, 147, 148, 149]
    print("=" * 58)

    if not DATA_MAHASISWA:
        print("|                             TIDAK ADA DATA                             |")  # Sesuai modul [cite: 132]
        print("=" * 58)
        return

    no = 0
    # Menggunakan nama sebagai key untuk mengambil data
    for nama in sorted(DATA_MAHASISWA.keys()):
        no += 1
        data = DATA_MAHASISWA[nama]
        # Format output agar rapi
        print(
            f"| {no:<2} | {data['nim']:<7} | {nama:<14} | {data['tugas']:<5} | {data['uts']:<5} | {data['uas']:<5} | {data['akhir']:<5.2f} |"
            # Contoh output modul [cite: 151, 152, 153, 154]
        )
    print("=" * 58)


def tambah_data():
    """Menambah data mahasiswa baru."""
    print("\n--- Tambah Data ---")  # Sesuai modul [cite: 135]
    nim = input("NIM : ")  # Sesuai modul [cite: 136, 138]
    nama = input("Nama : ")  # Sesuai modul [cite: 137, 139]

    # Validasi dan input nilai
    try:
        tugas = float(input("Nilai Tugas : "))  # Sesuai modul [cite: 142]
        uts = float(input("Nilai UTS : "))  # Sesuai modul [cite: 140]
        uas = float(input("Nilai UAS : "))  # Sesuai modul [cite: 141]
    except ValueError:
        print("Input nilai harus berupa angka!")
        return

    # Hitung nilai akhir
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)

    # Simpan data ke dictionary
    DATA_MAHASISWA[nama] = {
        'nim': nim,
        'tugas': tugas,
        'uts': uts,
        'uas': uas,
        'akhir': nilai_akhir
    }
    print(f"\nData mahasiswa '{nama}' berhasil ditambahkan!")


def ubah_data():
    """Mengubah data mahasiswa berdasarkan Nama."""
    print("\n--- Ubah Data ---")
    nama_cari = input("Masukkan Nama mahasiswa yang ingin diubah: ")

    if nama_cari in DATA_MAHASISWA:
        data = DATA_MAHASISWA[nama_cari]
        print(f"\nData saat ini untuk {nama_cari}:")
        print(f"NIM: {data['nim']}, Tugas: {data['tugas']}, UTS: {data['uts']}, UAS: {data['uas']}")

        # Ubah nilai
        try:
            data['nim'] = input(f"Ubah NIM (lama: {data['nim']}): ") or data['nim']
            data['tugas'] = float(input(f"Ubah Nilai Tugas (lama: {data['tugas']}): ") or data['tugas'])
            data['uts'] = float(input(f"Ubah Nilai UTS (lama: {data['uts']}): ") or data['uts'])
            data['uas'] = float(input(f"Ubah Nilai UAS (lama: {data['uas']}): ") or data['uas'])
        except ValueError:
            print("Input nilai harus berupa angka! Pembatalan Ubah Data.")
            return

        # Hitung ulang nilai akhir
        data['akhir'] = hitung_nilai_akhir(data['tugas'], data['uts'], data['uas'])
        print(f"\nData mahasiswa '{nama_cari}' berhasil diubah!")
    else:
        print(f"Data mahasiswa dengan nama '{nama_cari}' tidak ditemukan.")


def hapus_data():
    """Menghapus data mahasiswa berdasarkan Nama."""
    print("\n--- Hapus Data ---")
    nama_hapus = input("Masukkan Nama mahasiswa yang ingin dihapus: ")

    if nama_hapus in DATA_MAHASISWA:
        del DATA_MAHASISWA[nama_hapus]  # Menghapus elemen dictionary
        print(f"\nData mahasiswa '{nama_hapus}' berhasil dihapus!")
    else:
        print(f"Data mahasiswa dengan nama '{nama_hapus}' tidak ditemukan.")


def cari_data():
    """Mencari data mahasiswa berdasarkan Nama atau NIM."""
    print("\n--- Cari Data ---")
    kata_kunci = input("Masukkan Nama atau NIM mahasiswa yang dicari: ").lower()

    hasil_cari = {}
    for nama, data in DATA_MAHASISWA.items():
        # Cek apakah kata kunci ada di Nama atau NIM
        if kata_kunci in nama.lower() or kata_kunci in data['nim'].lower():
            hasil_cari[nama] = data

    if hasil_cari:
        print("\n--- Hasil Pencarian ---")
        print("=" * 58)
        print("| NO |   NIM   |      NAMA      | TUGAS |  UTS  |  UAS  | AKHIR |")
        print("=" * 58)
        no = 0
        for nama in hasil_cari.keys():
            no += 1
            data = hasil_cari[nama]
            print(
                f"| {no:<2} | {data['nim']:<7} | {nama:<14} | {data['tugas']:<5} | {data['uts']:<5} | {data['uas']:<5} | {data['akhir']:<5.2f} |"
            )
        print("=" * 58)
    else:
        print(f"Tidak ada data mahasiswa yang cocok dengan '{kata_kunci}'.")


def main():
    """Fungsi utama untuk menjalankan program."""
    while True:
        pilihan = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari (K)eluar]:").lower()  # Sesuai modul [cite: 127]

        if pilihan == 'l':
            tampilkan_data()
        elif pilihan == 't':
            tambah_data()
        elif pilihan == 'u':
            ubah_data()
        elif pilihan == 'h':
            hapus_data()
        elif pilihan == 'c':
            cari_data()
        elif pilihan == 'k':
            print("Program selesai. Sampai jumpa!")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")


if __name__ == "__main__":
    main()
```

## hasil
<img width="1919" height="819" alt="image" src="https://github.com/user-attachments/assets/5b8ea799-8665-4899-8a21-498df1ae7aae" />
<img width="1383" height="754" alt="image" src="https://github.com/user-attachments/assets/2d7f718f-95f7-4ba0-bcc9-01fc2a70b2ba" />
