TABEL ACADEMY — WEBSITE BOOKING DEMO

File utama: index.html
Nomor WhatsApp admin yang terpasang: 62881025605918

ISI DEMO
- Beranda, sejarah Tabel Academy, program bimbel, profil tutor, area testimoni, price list, dan form booking.
- Form mengutamakan Kak Dias dan memuat Kak Annas/Kak Syifa sebagai alternatif.
- Form WhatsApp menyiapkan pesan berisi data siswa dan pilihan jadwal.

PENTING: INI MASIH PROTOTIPE FRONT-END
- Slot waktu yang muncul adalah contoh, bukan data Google Calendar live.
- Booking belum disimpan ke database dan belum mengunci slot.
- Jangan dipublikasikan untuk menerima booking sungguhan sebelum integrasi backend, database, dan Google Calendar selesai.
- Testimoni saat ini berupa placeholder, harus diganti dengan testimoni asli yang sudah mendapat izin.
- Harga yang tercantum adalah harga acuan dari informasi awal; admin perlu memverifikasi tarif/paket sebelum publikasi.

CARA KERJA INTEGRASI GOOGLE CALENDAR YANG DISARANKAN
1. Buat project Google Cloud khusus website dan aktifkan Google Calendar API.
2. Siapkan kalender kerja Kak Dias, Kak Annas, Kak Syifa. Bagikan akses yang sesuai kepada akun integrasi website; jangan bagikan password Google.
3. Website/backend menggunakan Calendar API FreeBusy untuk memeriksa jadwal tiap tutor. Periksa Kak Dias dulu.
4. Jika ada slot cocok, tampilkan slot Kak Dias. Jika tidak ada slot sesuai rentang tanggal/waktu yang diminta, baru periksa dan tampilkan slot Kak Annas dan Kak Syifa.
5. Saat siswa menekan konfirmasi, backend harus mengecek ulang slot dan membuat event di kalender yang tepat secara atomik/secepat mungkin agar mencegah double booking. Simpan status booking dan event ID di database.
6. Kirim ringkasan ke WhatsApp admin melalui tautan wa.me. Tautan hanya menyiapkan pesan; siswa tetap perlu menekan tombol Kirim. Untuk mengirim otomatis, dibutuhkan WhatsApp Business Platform/API.
7. Gunakan backend/serverless function untuk menyimpan kredensial OAuth/service account dan rahasia API. Jangan pernah menaruh secret di HTML/JavaScript publik.

ALUR DATA SISWA YANG DISARANKAN
Nama lengkap, nomor WA, sekolah/kampus, jurusan, kelas/semester, program, mata kuliah/materi, tutor, tanggal, jam, durasi, catatan, status booking, status pembayaran, Calendar Event ID.

LANGKAH BERIKUTNYA
- Tentukan hosting (misalnya Vercel/Netlify/Replit) dan subdomain awal yang akan digunakan.
- Siapkan akses/kalender tutor dan tentukan kalender mana yang menjadi sumber jadwal.
- Finalisasi price list, profil tutor, dan testimoni.
- Bangun backend + database + integrasi Calendar API sebelum menerima booking live.
