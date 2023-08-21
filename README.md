# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. Devops merupakan pengembangan dari metode agile dengan melakukan kolaborasi dan komunikasi antar tim untuk mengembangkan aplikasi dan melakukan delivery kepada client.

2. Infrastruktur merupakan dukungan teknologi dalam pengembangan , implementasi, pengujian, serta pengelolaan suatu perangkat lunak

3. Server merupakan sumber daya terpusat yang menyedialakn layanan pengelolaan informasi kepada sumber daya lain (komputer) dalam suatu jaringan. Sebagai contoh webserver Nginx yang menyajikan halaman web kepada pengguna melalui protokol HTTP.

4. Karena server memiliki peran penting yang memungkinkan para pengembang untuk mengintgrasikan serta melakukan pengujian terhadap perangkat lunak yang dikembangkannya.

5. Virtualisasi merupakan mesin vitual yang memungkinkan sistem operasi berjalan secara terisolasi / terpisah di atas suatu hardware. Sedangkan container memungkinkan lingkungan runtaime terisolasi diatas suatu hardware

6. Container unggul dalam aspek portabilitas antar environment, efisiensi dengan mengurangi overhead,serta skalabilitas dengan cepat diperbanyak untuk menangani perubahan traffic.

7. Orchestration Container merupakan suatu sistem untuk mengotomatisasi dan mengelola aplikasi dalam lingkunkan container yang kompleks dan dinamis.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy

(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container

- image: `dimmaryanto93/udemy-springboot-app:latest`
- port: `8080`
- env:
  - `DATABASE_HOST`: `<ip-domain-db>`
  - `DATABASE_PORT`: `5432`
  - `DATABASE_NAME`: `<db-name>`
  - `DATABASE_PASSWORD`: `<db-password>`
  - `APPLICATION_PORT`: `8080`
    need:
  - Database PostgreSQL v14.2

2. Frontend container

- image: `dimmaryanto93/udemy-angular-app:latest`
- port: `80`
- env:
  - `APPLICATION_PORT`: `80`
  - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
  - `BACKEND_HOST`: `<ip-backend-apps>`
  - `BACKEND_PORT`: `<port-backend-apps>`
  - `BACKEND_CONTEXT_PATH`: `/`
- need:
  - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`
