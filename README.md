# Webprofile Django

Proyek ini adalah website profil berbasis Django dengan aplikasi utama `santri`.

## Ringkasan

Aplikasi ini menampilkan profil digital seorang santri, dengan halaman:
- Beranda
- Biodata
- Jadwal
- Galeri
- Feedback

Website menggunakan Django 6.0.4, basis data SQLite, dan template HTML sederhana.

## Struktur Folder

```
webprofile/
├── db.sqlite3
├── manage.py
├── README.md
├── santri/
│   ├── admin.py
│   ├── apps.py
│   ├── migrations/
│   │   └── __init__.py
│   ├── models.py
│   ├── templates/
│   │   └── biodata.html
│   ├── tests.py
│   ├── urls.py
│   ├── views.py
│   └── __init__.py
├── static/
│   ├── image/
│   │   ├── foto.jpg
│   │   └── logo (1).webp
│   └── style.css
├── templates/
│   ├── base.html
│   └── home.html
└── webprofile/
    ├── __init__.py
    ├── asgi.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

> Catatan: Struktur di atas dibuat berdasarkan isi folder saat ini. Jika ada file template tambahan di `santri/templates/`, silakan tambahkan ke daftar.

## Penjelasan Folder Utama

- `manage.py`
  - Perintah utama untuk menjalankan server, migrasi database, dan tugas Django.

- `webprofile/`
  - Folder project Django.
  - `settings.py`: konfigurasi Django, termasuk `INSTALLED_APPS`, database, static files, dan template.
  - `urls.py`: rute global, mengarahkan URL root ke `santri.urls`.
  - `wsgi.py` / `asgi.py`: pintu masuk untuk deployment.

- `santri/`
  - Aplikasi Django utama.
  - `views.py`: fungsi view untuk render halaman.
  - `urls.py`: urlpattern untuk halaman `home`, `biodata`, `jadwal`, `galeri`, `feedback`.
  - `templates/`: menyimpan template aplikasi khusus. Saat ini ada `biodata.html`.

- `templates/`
  - Template global.
  - `base.html`: layout utama halaman, header, menu navigasi, dan footer kontak.
  - `home.html`: halaman utama beranda.

- `static/`
  - File statis seperti CSS dan gambar.
  - `style.css`: styling halaman.
  - `image/`: menyimpan aset gambar seperti `foto.jpg` dan `logo (1).webp`.

- `db.sqlite3`
  - Basis data SQLite default.

## Hal-hal Penting

- `INSTALLED_APPS` di `webprofile/settings.py` berisi aplikasi `santri` dan default Django apps.
- Template global menggunakan `DIRS = [BASE_DIR / 'templates']` sehingga semua template di folder `templates/` dapat dipanggil.
- `STATICFILES_DIRS` mengarah ke folder `static/` supaya CSS dan image dapat diload melalui `{% static %}`.
- `DEBUG = True` artinya konfigurasi ini hanya cocok untuk pengembangan, bukan produksi.

## Routing / URL

Rute yang tersedia di aplikasi:
- `/` → halaman `home`
- `/biodata/` → halaman `biodata`
- `/jadwal/` → halaman `jadwal`
- `/galeri/` → halaman `galeri`
- `/feedback/` → halaman `feedback`

## Cara Menjalankan

1. Pastikan Python dan Django terpasang.
2. Aktifkan lingkungan virtual (opsional tapi disarankan).
3. Jalankan:

```bash
python manage.py runserver
```

4. Buka `http://127.0.0.1:8000/` di browser.

## Perbaikan atau Penambahan

Beberapa rekomendasi jika ingin mengembangkan proyek ini:
- Tambahkan semua halaman template yang belum ada di folder `santri/templates/`.
- Buat `models.py` jika ingin menyimpan data dinamis seperti feedback pengguna.
- Tambahkan form Django di halaman `feedback` untuk menerima input pengguna.
- Siapkan `requirements.txt` untuk manajemen dependensi.

## Kontak & Sumber

Proyek ini adalah website profil digital untuk kebutuhan portofolio santri.
Jika ingin memperluas, gunakan paradigma Django standar: model → view → template → URL.
