# Public HTTP Server with Nginx + Ngrok

This project runs a simple **Nginx HTTP server locally** and exposes it to the public internet using **Ngrok**, all managed with **Docker Compose**.

## ✨ Purpose

* Serve static files locally using Nginx
* Expose the local server to the public via an Ngrok tunnel
* No application runtime required (pure Nginx)

---

## 📁 Project Structure

```
.
├── docker-compose.yaml
├── template.env
├── public_html/          # Static files served by Nginx
├── templates/            # Nginx config templates
│   └── default.conf.template
└── LICENSE
```

---

## ⚙️ Requirements

* Docker
* Docker Compose
* Ngrok account (for the auth token)

---

## 🔧 Configuration

1. Copy the environment template:

```bash
cp template.env .env
```

2. Edit `.env` and set your Ngrok auth token:

```env
NGROK_AUTHTOKEN=your_ngrok_token_here
```

You can also customize the Ngrok URL, ports, or command if needed.

---

## 🚀 Usage

Start the services:

```bash
docker compose up
```

* Nginx will run locally on `http://localhost:80`
* Ngrok will expose it publicly using the configured URL

Once running, Ngrok will forward traffic to:

```
http-server:80
```

---

## 📌 Notes

* Static files should be placed in `public_html/`
* Nginx configuration is templated using `templates/default.conf.template`
* This setup is ideal for quick demos, testing, or temporary public access

---

## 🛑 Stop Services

```bash
docker compose down
```

---

## 📄 License

See the `LICENSE` file for details.

