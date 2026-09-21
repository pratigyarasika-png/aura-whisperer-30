# Refactoring Infinity dan Kanvas Utama

## Hasil yang akan dibangun
- Mengganti seluruh branding yang terlihat dari **Orbis/Orbit** menjadi **Infinity**, termasuk judul halaman, metadata, label navigasi, teks bantuan, dan identitas asisten.
- Mempertahankan nama kunci penyimpanan lama secara internal agar dokumen, riwayat, tema, dan proyek pengguna yang sudah tersimpan tidak hilang.
- Menata ulang node **Data Suite** ke kiri-bawah dan memotong busur hanya pada sisi dekat papan AI secara halus, sehingga lingkaran tetap terbaca, papan tetap utuh, dan simetri terjaga pada desktop maupun layar di bawah 640px.
- Menjadikan **General AI** sebagai mode awal setiap kali halaman utama dibuka. Tombol kaca pembesar akan fokus ke kolom pertanyaan atau menjalankan pertanyaan di kanvas, bukan memindahkan pengguna ke halaman pencarian.
- Menambahkan 12 modul fitur di bawah area pertanyaan, dikelompokkan menjadi **Riset & Literatur**, **Penulisan & Dokumen**, dan **Analisis & Data**. Setiap modul memakai ikon Lucide, kartu mint/putih, batas halus, dan tujuan yang sesuai ke fitur aplikasi yang sudah ada.
- Menambahkan **Equation Scanner** dengan ikon Sigma/Scan: pengguna dapat mengunggah atau memotret persamaan, mendapatkan hasil pembacaan dan bentuk LaTeX, lalu menyalinnya atau membukanya di ruang penulisan seperti alur aplikasi Photomath.
- Menyelaraskan ikon, badge, tipografi serif/sans, warna mint–teal, dan header pada halaman analisis agar konsisten dengan identitas Infinity.

## Perilaku modul
- Modul yang sudah memiliki halaman akan membuka halaman terkait: pencarian, penulisan, analisis, data & coding, atau konverter.
- Modul yang merupakan aksi AI akan mengisi/fokuskan pertanyaan utama atau membuka ruang kerja paling relevan, tanpa menambahkan penyimpanan server baru.
- Equation Scanner menggunakan pembacaan gambar yang sudah tersedia, menampilkan status, hasil, dan penanganan kesalahan yang jelas tanpa mengubah arsitektur penyimpanan client-side.

## Detail teknis
- Tetap memakai LocalStorage/IndexedDB yang ada; tidak menambah database atau login baru.
- Token warna global dipakai untuk semua warna UI baru; tidak menaruh warna mentah di komponen.
- Penyebutan internal yang tidak terlihat dan menjadi bagian kompatibilitas data/format (misalnya storage key dan class ekspor lama) tidak diubah.
- Validasi akhir mencakup pemeriksaan branding, TypeScript/build, interaksi tombol pencarian dan Equation Scanner, serta tampilan desktop dan mobile.
