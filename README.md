# Vidora

Situs video dewasa berbasis URL: Cloudflare Pages + Pages Functions + Supabase. Video tidak diunggah, hanya ditautkan.

## Pasang
1. Supabase > SQL Editor, jalankan berurutan: `supabase-sql/schema.sql`, `thumb_time.sql`, `aspect.sql` (aman dijalankan ulang).
2. Authentication > Users: buat user admin, lalu jalankan baris `insert into site_admins ...` di bagian bawah `schema.sql` dengan emailnya.
3. Edit `js/config.js` (`SITE`, `CONTACT_EMAIL`, URL dan kunci anon Supabase) dan alamat sitemap di `robots.txt`.
4. Push ke GitHub dan hubungkan ke Cloudflare Pages (folder `functions/` ikut terdeploy). Variabel `SUPABASE_URL`, `SUPABASE_KEY`, `SITE_NAME` bersifat opsional.
5. Buka `/admin`, tambah kategori dan video.
6. Google Search Console: verifikasi domain, kirim `/sitemap.xml`.

## Fitur admin
- Tambah video lewat URL: mp4/webm langsung, embed, atau Google Drive (otomatis jadi embed).
- Thumbnail diambil langsung dari video (simpan detik frame saja): otomatis atau pilih manual lewat slider. URL thumbnail manual tetap bisa diisi.
- Rasio video (16:9, 9:16, dst) terdeteksi otomatis; ubah manual bila salah.
- Wajib isi asal/lisensi konten dan pernyataan 18+/persetujuan; database menolak video tanpa itu.
- Laporan konten dari pengunjung muncul di tab Laporan.

## Alamat
`/` beranda, `/?c=kategori`, `/?q=kata`, `/v/judul-<id>` video, `/report`, `/terms`, `/privacy`, `/admin`, `/sitemap.xml`.
