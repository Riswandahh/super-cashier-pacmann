# super-cashier-pacmann
Final Project Python - Super Cashier System
# Latar Belakang Problem
Sistem Kasir Self-Service untuk supermarket yang memungkinkan customer untuk mengelola transaksi belanja secara mandiri. Pengguna dapat melakukan berbagai macam operasi pada keranjang belanja mereka, seperti menambah, mengubah, dan menghapus item, serta menghitung total belanja dengan diskon otomatis.
# Penjelasan Requirements/Objectives
Sistem ini memiliki beberapa tujuan atau kebutuhan utama untuk mencapai fungsionalitas yang optimal. Berikut adalah penjelasan mengenai apa saja yang perlu dilakukan dalam pembuatan sistem ini:
1. Membuat Transaksi Baru: Ketika pelanggan mulai berbelanja, sistem akan membuat transaksi baru di mana barang-barang yang akan dibeli akan dimasukkan ke dalam transaksi tersebut.
2. Membuat Transaksi Baru: Ketika pelanggan mulai berbelanja, sistem akan membuat transaksi baru di mana barang-barang yang akan dibeli akan dimasukkan ke dalam transaksi tersebut.
3. Menghitung Total Harga dengan Sistem Diskon: Setelah barang-barang ditambahkan ke dalam keranjang, sistem akan menghitung total harga yang harus dibayar, dengan mempertimbangkan diskon berdasarkan total harga belanja: a. Diskon 10% untuk total lebih dari Rp 500,000. b. Diskon 8% untuk total lebih dari Rp 300,000. c. Diskon 5% untuk total lebih dari Rp 200,000. d. Tanpa diskon jika total belanja kurang dari Rp 200,000.
4. Menampilkan Detail Pembelian dan Pembayaran: Sistem akan menampilkan rincian pembelian secara jelas, termasuk nama barang, jumlah barang, harga per unit, dan total harga untuk setiap barang. Selain itu, sistem juga akan memberikan detail pembayaran, termasuk diskon yang diterima.
5. Memastikan Data Transaksi Valid: Sebelum menghitung total dan melakukan pembayaran, sistem akan memeriksa apakah semua data yang dimasukkan oleh pengguna valid. Misalnya, nama barang harus berupa teks, jumlah barang harus angka positif, harga barang harus sesuai, dan total harga harus konsisten dengan jumlah barang dan harga per unit.
# Penjelasan Alur Code
1. Transaksi Baru: Pengguna memulai dengan membuat transaksi baru. Keranjang belanja kosong.
2. Menambah Item: Pengguna menambah barang dengan memberikan nama barang, jumlah yang dibeli, dan harga per unit.
3. Update Item: Pengguna bisa mengubah nama barang, jumlah barang, atau harga barang sesuai kebutuhan.
4. Menghapus Item: Barang yang sudah tidak diperlukan bisa dihapus dari keranjang belanja.
5. Cek Pesanan: Sistem memverifikasi apakah semua data transaksi valid dan tidak ada kesalahan input.
6. Menghitung Total: Sistem menghitung total belanja, dengan memperhitungkan diskon sesuai dengan aturan yang ada.
7. Pembayaran: Sistem menampilkan total yang harus dibayar oleh pengguna, beserta rincian diskon yang diterima.
# Penjelasan Mengenai Functions atau Attribute
1. Transaction adalah kelas utama yang mengelola proses transaksi belanja. Berikut adalah atribut dan fungsi penting dalam kelas ini:
2. Attributes (Atribut):
items: Ini adalah dictionary yang menyimpan data barang yang dibeli. Format data dalam dictionary ini adalah:

a. Nama barang: kunci (key)

b. Value: list yang berisi:

c. Jumlah barang

d. Harga per unit

e. Total harga barang (jumlah x harga per unit)

3. Functions (Fungsi):
    
a. __init__(): Fungsi ini digunakan untuk menginisialisasi objek transaksi baru dengan keranjang belanja yang kosong.

b. add_item(item_data): Fungsi ini menambahkan barang baru ke dalam keranjang belanja. Fungsi ini memeriksa apakah input yang diberikan valid dan menghitung total harga barang yang ditambahkan.

c. update_item_name(nama_item, update_nama_item): Fungsi ini digunakan untuk mengganti nama barang dalam keranjang belanja.

d. update_item_qty(nama_item, update_jumlah_item): Fungsi ini digunakan untuk mengganti jumlah barang yang ada dalam keranjang belanja. Fungsi ini juga menghitung ulang total harga barang setelah perubahan jumlah.

e. update_item_price(nama_item, update_harga_item): Fungsi ini digunakan untuk mengubah harga per unit barang dalam keranjang belanja, serta menghitung ulang total harga setelah perubahan harga.

f. delete_item(nama_item): Fungsi ini digunakan untuk menghapus barang dari keranjang belanja.

g. reset_transaction(): Fungsi ini menghapus semua barang dalam keranjang belanja, mengembalikan sistem ke keadaan awal.

h. check_order(): Fungsi ini memverifikasi apakah semua data dalam keranjang valid dan tidak ada kesalahan input.

i. total_price(): Fungsi ini menghitung total harga belanja setelah menerapkan diskon yang sesuai berdasarkan total belanja.
# Demonstrasi Code dengan Test Case yang Diberikan dan Outputnya
*Test Case 1: Menambahkan Item*

trnsct_123 = Transaction()
trnsct_123.add_item(["Ayam Goreng", 2, 20000])

![Screenshot 2025-06-30 164220](https://github.com/user-attachments/assets/051a6bc2-2acd-4da5-a11c-fed050cdd7e3)

*Test Case 2: Menghapus Item*

trnsct_123.delete_item("Pasta Gigi")

![Screenshot 2025-06-30 164645](https://github.com/user-attachments/assets/9eef6bc9-6d5e-4168-b13b-81b72b20c853)

*Test Case 3: Reset Transaksi*

trnsct_123.reset_transaction()

![Screenshot 2025-06-30 164657](https://github.com/user-attachments/assets/2b66d8de-596c-434d-b7cd-7b1bfc3ca256)


*Test Case 4: Menghitung Total Belanja*

trnsct_123.add_item(["Ayam Goreng", 2, 20000])
trnsct_123.add_item(["Pasta Gigi", 3, 15000])
trnsct_123.add_item(["Mainan Mobil", 1, 200000])
trnsct_123.add_item(["Mi Instan", 5, 3000])

total = trnsct_123.total_price()


![Screenshot 2025-06-30 164726](https://github.com/user-attachments/assets/dcc85661-4f48-48a4-9f22-c3eb09be84c8)


![Screenshot 2025-06-30 164749](https://github.com/user-attachments/assets/796addc4-adbc-4ce9-8a54-de93aa0f67f6)


![Screenshot 2025-06-30 164815](https://github.com/user-attachments/assets/090e2505-bbbc-48e6-bb6c-31838ff1e533)

*Test Case Tambahan: Update Item*

![Screenshot 2025-06-30 164919](https://github.com/user-attachments/assets/9c863060-9efe-460d-8446-76b009a0ece1)


![Screenshot 2025-06-30 165037](https://github.com/user-attachments/assets/9d5a9d43-64e5-46ea-87f4-e6b7ce5efd9e)

#Conclusion
Sistem kasir ini memberikan solusi self-service yang praktis untuk pelanggan supermarket. Dengan kemampuan untuk menambah, mengubah, dan menghapus item secara langsung, serta menghitung total pembelian dengan diskon otomatis, pengguna dapat dengan mudah mengelola transaksi belanja mereka tanpa perlu bantuan kasir. Sistem ini memastikan bahwa transaksi dilakukan dengan cepat dan tepat, sambil memverifikasi keakuratan data yang dimasukkan.
