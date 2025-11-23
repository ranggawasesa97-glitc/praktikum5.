# kode pemerograman (Latihan1.py)
```python
daftar_kontak = {
    "Ari": "081267888",
    "Dina": "0876777776"
}
print(f"1. Dictionary awal: {daftar_kontak}")
print("Nama | Nomor telepon")
print("====================")
print(f"Ari  |",f"{daftar_kontak['Ari']}")
print(f"Dina |",f"{daftar_kontak['Dina']}")

print("2. Tampilkan kontaknya Ari:")
nomor_ari = daftar_kontak["Ari"]
print(f"Nomor Ari: {nomor_ari}")

print("3. Tambah kontak baru Riko:")
daftar_kontak["Riko"] = "087654544"
print(f"Dictionary setelah penambahan Riko: {daftar_kontak}")

print("4. Ubah kontak Dina:")
daftar_kontak["Dina"] = "088999776"
print(f"Dictionary setelah perubahan Dina: {daftar_kontak}")

print("5. Tampilkan semua Nama (keys):")
semua_nama = daftar_kontak.keys()
print(f"Daftar Nama: {list(semua_nama)}")

print("6. Tampilkan semua Nomor (values):")
semua_nomor = daftar_kontak.values()
print(f"Daftar Nomor: {list(semua_nomor)}")

print("7. Tampilkan daftar Nama dan nomornya (items):")
for nama, nomor in daftar_kontak.items():
    print(f" {nama}, | {nomor}")

print("8. Hapus kontak Dina:")
del daftar_kontak["Dina"]
print(f"Dictionary setelah menghapus Dina: {daftar_kontak}")
```
# hasil otput
<img width="1433" height="853" alt="Screenshot 2025-11-23 081345" src="https://github.com/user-attachments/assets/83962eb5-e2ad-4efa-8d77-b088b7dfaa90" />

