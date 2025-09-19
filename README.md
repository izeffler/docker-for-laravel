# 🚀 Docker for Laravel

[![Docker](https://img.shields.io/badge/Docker-Compose-blue?logo=docker)](https://www.docker.com/)

Credits: [@Pansiere](https://github.com/Pansiere)

---

## 📖 Overview

This project provides a **Docker environment for Laravel** that simplifies the setup of your local development environment.  

✅ Runs **Laravel + PHP + MySQL + phpMyAdmin**  
✅ **Vite** runs automatically in the background (no need to run `npm run dev`)  
✅ Pre-configured containers for faster development  

---

## ⚡ Requirements

- [Docker](https://docs.docker.com/get-docker/) installed  
- [Docker Compose](https://docs.docker.com/compose/install/) installed  
- Laravel project (existing or new)  

---

## 🛠️ Installation

1. Clone this repository into your Laravel project root:

```bash
git clone git@github.com:izeffler/docker-for-laravel.git
```

2. Update your Laravel `.env` database configuration:

```dotenv
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=your_database
DB_USERNAME=root
DB_PASSWORD=password
```

3. Prepare your `vite.config.js` file and configure it with the following server options:

```bash
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import tailwindcss from '@tailwindcss/vite';

export default defineConfig({
    plugins: [
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
        tailwindcss(),
    ],
    server: {
        host: '0.0.0.0',
        port: 5173,
        hmr: {
            host: 'localhost',
            port: 5173,
        }
    }
});
```

4. Build and start Docker containers:

```bash
docker compose up -d --build
```

---

## 🌐 Services & Access

* Laravel app: [http://localhost](http://localhost)
* phpMyAdmin: [http://localhost:8080](http://localhost:8080) (auto login enabled)

---

## 🐳 Container Access

Open a PHP container shell:

```bash
docker exec -it php bash
```

Run MySQL commands inside the MySQL container:

```bash
docker exec -i mysql -uroot -ppassword
```

---

## 💡 Tips

* To rebuild containers after changes:

  ```bash
  docker compose up -d --build
  ```

* To stop containers:

  ```bash
  docker compose down
  ```

* To reset everything (including database data):

  ```bash
  docker compose down -v
  ```

---

## 📜 License

This project is open-sourced under the [MIT license](LICENSE).

