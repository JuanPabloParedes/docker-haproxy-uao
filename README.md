
# 🐳 Proyecto Docker HAProxy - UAO

**Proyecto realizado por Juan Pablo Paredes**  
**Universidad Autónoma de Occidente - Facultad de Ingeniería**

---

## 📘 Descripción General

Este proyecto implementa una **arquitectura de balanceo de carga** utilizando **HAProxy** dentro de un entorno **Docker**, con varios servicios backend y frontend simulando una aplicación distribuida.  
El objetivo académico es **demostrar el funcionamiento del balanceador de carga y su impacto en el rendimiento** mediante pruebas de estrés con **Apache JMeter**.

---

## 🧩 Arquitectura del Sistema

La arquitectura se compone de los siguientes contenedores:

| Servicio     | Imagen Base      | Puerto Externo | Descripción |
|---------------|------------------|----------------|--------------|
| `haproxy`     | haproxy:latest   | 8080           | Balanceador de carga que distribuye el tráfico hacia los backends. |
| `backend_1`   | python:3.10 / Node | 5001          | Primer servicio backend con respuesta JSON simple. |
| `backend_2`   | python:3.10 / Node | 5002          | Segundo servicio backend idéntico para balanceo. |
| `frontend`    | nginx:alpine     | 80             | Interfaz simple que se comunica con los backends. |

📂 **Estructura de carpetas:**
docker-haproxy-uao/
│
├── backend/
│ ├── app.py
│ └── Dockerfile
│
├── haproxy/
│ ├── haproxy.cfg
│ └── Dockerfile
│
├── frontend/
│ └── index.html
│
├── docker-compose.yml
└── README.md

---

## ⚙️ Configuración y Ejecución

### 1️⃣ Clonar el repositorio
```bash
git clone https://github.com/juan_pab_pds_gmz/docker-haproxy-uao.git
cd docker-haproxy-uao
