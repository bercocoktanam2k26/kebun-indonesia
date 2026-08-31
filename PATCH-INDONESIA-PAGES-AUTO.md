# PATCH — Indonesia Pages Auto Generate V3

Patch ini mempertahankan arsitektur yang ada:
- RepoPilot tetap menulis videos.json + cover melalui Worker/GitHub App.
- Cloudflare Worker tidak diubah.
- GitHub App tidak diubah.
- Secrets tidak diubah.
- Adsterra tidak diubah.

Perubahan hanya pada GitHub Actions repository indonesia:
1. Menjalankan generate.py setiap push/manual run.
2. Memastikan setiap entry videos.json menghasilkan `{slug}.html`.
3. Memastikan setiap ogImage menggunakan https://viral18plus.github.io/indonesia/covers/.
4. Jika generator gagal membuat halaman video, deployment dibatalkan agar homepage tidak menghasilkan link 404.

Setelah workflow dipasang, jalankan workflow sekali secara manual dari Actions untuk membuat halaman video terbaru yang sudah ada di videos.json.
