# HPP Salasatu Coffee (@salasatucoffee)

Aplikasi HPP untuk kedai minuman: bahan, resep, menu, biaya tambahan, dan target bulanan.
Proyek ini membungkus aplikasi web di folder `www` menjadi aplikasi Android (APK) dengan Capacitor.

## Cara 1: Bangun APK otomatis di GitHub (tanpa Android Studio)

1. Buat akun di github.com, lalu buat repository baru (boleh Private).
2. Unggah seluruh isi folder ini ke repository, termasuk folder `.github`
   (tombol "Add file" > "Upload files", seret semua file dan folder).
3. Buka tab **Actions**, pilih **Build APK**, klik **Run workflow**.
4. Tunggu 5-10 menit sampai centang hijau. Buka run tersebut, unduh **HPP-Salasatu-apk** di bagian Artifacts, lalu ekstrak file zip-nya.
5. Kirim `app-debug.apk` ke HP, buka, dan izinkan pemasangan dari sumber ini.

## Cara 2: Bangun di komputer sendiri

Butuh Node.js 22 dan Android Studio (sudah termasuk JDK).

    npm install
    npx cap add android
    npx capacitor-assets generate --android --iconBackgroundColor "#1E6B57" --iconBackgroundColorDark "#1E6B57"
    npx cap sync android
    npx cap open android

Di Android Studio pilih Build > Build APK(s).

## Mengubah isi aplikasi

Edit `www/index.html`, lalu jalankan ulang langkah build. Nama aplikasi dan ID paket ada di `capacitor.config.json`.

## Untuk Google Play Store

File `app-debug.apk` hanya untuk dipasang langsung. Play Store butuh paket AAB yang ditandatangani dengan kunci rilis:

1. Daftar Google Play Console (biaya pendaftaran sekali bayar, sekitar USD 25).
2. Di Android Studio pilih Build > Generate Signed Bundle / APK, pilih Android App Bundle, buat keystore baru dan simpan baik-baik.
3. Unggah file `.aab` ke Play Console, isi data toko (deskripsi, tangkapan layar, kebijakan privasi), lalu kirim untuk ditinjau.

## Catatan

Data aplikasi tersimpan di penyimpanan aplikasi pada HP. Gunakan fitur "Salin cadangan" di tab Biaya sebelum menghapus aplikasi.
