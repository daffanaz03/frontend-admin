# Panduan Penamaan Branch dan Commit

Dalam proyek ini, pembuatan branch **wajib** menggunakan format terstruktur yang selalu dimulai dari salah satu modul utama: `order` atau `pencatatan`. Setelah itu, tentukan layer yang dikerjakan, dan akhiri dengan nama fitur spesifik.

**Format Baku Branch:**
`[modul_utama]/[layer]/[nama_fitur]`

---

## Struktur Branch

order
	-> order/frontend
		-> order/frontend/dashboard
		-> order/frontend/form-checkout
	-> order/backend
		-> order/backend/api-transaction
		-> order/backend/payment-gateway

pencatatan
	-> pencatatan/frontend
		-> pencatatan/frontend/tabel-kompen
		-> pencatatan/frontend/filter-pencarian
	-> pencatatan/backend
		-> pencatatan/backend/sync-command
		-> pencatatan/backend/model-replika
		-> pencatatan/backend/index-query

---

## Penjelasan dan Aturan Penamaan Branch

1. **[modul_utama]**: Titik awal branch. Hanya boleh menggunakan salah satu dari dua opsi berikut:
   * `order` (Untuk pengembangan terkait pesanan/transaksi)
   * `pencatatan` (Untuk pengembangan sistem kehadiran, kompen, dan sinkronisasi data akasia)

2. **[layer]**: Lingkup pengerjaan secara teknis:
   * `frontend` (Untuk urusan UI, Dashboard, form, Blade/Vue/React)
   * `backend` (Untuk urusan Controller, Model, Routing, Command `akasia:sync`, koneksi DB)

3. **[nama_fitur]**: Nama fitur spesifik yang sedang dikembangkan. 
   * Gunakan huruf kecil seluruhnya (*lowercase*).
   * Pisahkan antar kata menggunakan tanda strip (`-`).
   * *Contoh yang benar:* `sync-command`, `export-pdf`, `tabel-kompen`.

**Contoh Command Git:**
Jika Anda ingin mengerjakan logic sinkronisasi database untuk modul pencatatan, gunakan perintah berikut:
`git checkout -b pencatatan/backend/sync-command`

---

## Aturan Penulisan Commit (Commit Message)

Setiap melakukan `git commit`, **wajib** menyertakan nama/username Anda di dalam kurung siku `[ ]` pada **akhir** pesan commit. Ini bertujuan agar lebih mudah melacak siapa yang mengerjakan fitur atau perbaikan tertentu tanpa mengganggu konteks pesan di awal.

**Format Baku Commit:**
`Deskripsi singkat tentang apa yang diubah/ditambahkan [Nama Orang]`

**Contoh Commit yang Benar:**
* `git commit -m "Membuat UI tabel kehadiran kompen [Don]"`
* `git commit -m "Setup koneksi database mysql_web dan model replika [Daf]"`
* `git commit -m "Memperbaiki bug pada query index pencatatan [khairuonwork]"`