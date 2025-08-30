# 🚀 Qdrant Server dengan Docker Compose

Repositori ini menyediakan konfigurasi `docker-compose.yml` sederhana untuk menjalankan **Qdrant**, vector database open-source yang digunakan untuk pencarian semantik, sistem rekomendasi, dan aplikasi AI.

## 📦 Layanan

- **Qdrant Server**
  - API HTTP/REST tersedia di port `6333`
  - gRPC API tersedia di port `6334`
  - Data disimpan di volume Docker (atau host path)

---

## 🛠 Kebutuhan

- [Docker](https://docs.docker.com/get-docker/) (>= 20.x)
- [Docker Compose](https://docs.docker.com/compose/install/) (>= v2.x)

---

## ⚙️ Konfigurasi

Variabel lingkungan dapat disesuaikan menggunakan file `.env` atau langsung melalui shell.

| Variabel                | Nilai Default   | Deskripsi                       |
| ----------------------- | --------------- | ------------------------------- |
| `QDRANT_IMAGE_VERSION`  | `latest`        | Versi image Qdrant              |
| `QDRANT_CONTAINER_NAME` | `qdrant_server` | Nama container Docker           |
| `QDRANT_API_PORT`       | `6333`          | Port untuk API HTTP/REST Qdrant |
| `QDRANT_GRPC_PORT`      | `6334`          | Port untuk API gRPC Qdrant      |
| `QDRANT_DATA_PATH`      | `./.qdrant`     | Lokasi penyimpanan data di host |

Contoh file `.env`:

```env
QDRANT_IMAGE_VERSION=latest
QDRANT_CONTAINER_NAME=qdrant_server
QDRANT_API_PORT=6333
QDRANT_GRPC_PORT=6334
QDRANT_DATA_PATH=./
```

---

## ▶️ Cara Menjalankan

1. Clone repositori ini atau salin file `docker-compose.yml`.
2. Buat file `.env` (opsional, untuk konfigurasi kustom).
3. Jalankan Qdrant dengan perintah:

   ```bash
   docker-compose up -d
   ```

4. Hentikan Qdrant:

   ```bash
   docker-compose down
   ```

---

## 🌐 Akses Qdrant

- **Dashboard:**  
  `http://localhost:6333/dashboard`

- **API HTTP/REST:**  
  `http://localhost:6333`

- **gRPC API:**  
  `http://localhost:6334`

## 📚 Referensi

- [Dokumentasi Resmi Qdrant](https://qdrant.tech/documentation/)
- [Docker Hub: Qdrant](https://hub.docker.com/r/qdrant/qdrant)
