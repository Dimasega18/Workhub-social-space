# Cara Menjalankan Project Workhub (Docker + Java)

## 1. Persiapan (Requirement)
Sebelum menjalankan project ini, pastikan perangkat sudah memiliki:

- Docker Desktop
- Java JDK (minimal JDK 8, disarankan JDK 17)
- IDE Java (NetBeans / IntelliJ / VS Code)
- WinRAR / 7-Zip (untuk ekstrak file `.rar`)

---

## 2. Install Docker
1. Download dan install Docker Desktop
2. Setelah selesai install, buka Docker Desktop
3. Pastikan Docker dalam kondisi **Running**

Untuk memastikan Docker sudah aktif, buka CMD / Terminal lalu jalankan:

```bash
docker --version
docker ps
```

Jika muncul versi Docker dan daftar container (meskipun kosong), berarti Docker sudah berjalan.

---

## 3. Menjalankan Container
1. Masuk ke folder project yang berisi file `docker-compose.yml`
2. Jalankan perintah berikut:

```bash
docker compose up -d
```

3. Pastikan container sudah berjalan dengan perintah:

```bash
docker ps
```

Jika status container menunjukkan **Up**, berarti container berhasil dijalankan.

Jika ingin menghentikan container:

```bash
docker compose down
```

---

## 4. Ekstrak File RAR
1. Cari file project yang masih berbentuk `.rar`
2. Klik kanan file tersebut → pilih **Extract Here** atau **Extract to folder**
3. Setelah ekstrak selesai, akan muncul folder project Java hasil ekstrak

---

## 5. Menjalankan Workhub.java

### Cara yang paling disarankan (NetBeans)
1. Buka aplikasi **NetBeans**
2. Pilih menu **File → Open Project**
3. Pilih folder project hasil ekstrak
4. Cari file berikut:

```
src/main/java/com/mycompany/workhub/Workhub.java
```

5. Jalankan program dengan cara:
   - Klik tombol **Run (▶)**  
   atau
   - Klik kanan pada project → **Run**

---

## 6. Troubleshooting (Jika Terjadi Error)

### A. Container tidak berjalan
Cek log container dengan perintah:

```bash
docker compose logs -f
```

### B. Java tidak terdeteksi
Cek apakah Java sudah terinstall:

```bash
java -version
javac -version
```

Jika belum muncul versi, install Java JDK terlebih dahulu.

### C. Build sukses tapi UI tidak muncul
Pastikan file `Workhub.java` memiliki `main()` dan memanggil tampilan UI seperti:

- `setVisible(true)` (untuk Java Swing)

---

## 7. Catatan Penting
- Pastikan Docker container sudah berjalan dulu, karena aplikasi Workhub biasanya membutuhkan database/service dari container.
- Setelah container berjalan, baru jalankan file `Workhub.java`.
