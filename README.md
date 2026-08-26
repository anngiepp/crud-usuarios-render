# ⋆｡˚ ☁️ Render Cloud Deployment API & Static Site ⋆｡𖦹 ˚｡⋆

---

# 🧾 Descripción del Proyecto

Este laboratorio demuestra la implementación de una **Estrategia para la Nube** utilizando la plataforma **PaaS Render**, integrando el despliegue de aplicaciones web estáticas y servicios backend conectados a una base de datos administrada en la nube.

La solución está compuesta por dos aplicaciones independientes:

## 🌐 1. Perfil Web Personal (Static Site)

Página web estática desarrollada con **HTML5 y CSS3**, desplegada mediante el servicio **Static Site de Render**.

- 📂 Repositorio GitHub:  
  🔗 https://github.com/anngiepp/perfil-render

- 🚀 Aplicación desplegada en Render:  
  🔗 https://perfil-render-8x2p.onrender.com


## ⚙️ 2. API CRUD de Usuarios (Web Service)

API RESTful desarrollada con **Node.js y Express.js**, con persistencia de datos mediante una base de datos **PostgreSQL administrada por Render**.

Características principales:

- Gestión de usuarios mediante operaciones CRUD.
- Conexión segura mediante variables de entorno.
- Despliegue automático mediante integración con GitHub.
- Base de datos PostgreSQL en la nube.


- 📂 Repositorio GitHub:
  
  🔗 https://github.com/anngiepp/crud-usuarios-render

- 🚀 API desplegada en Render:

  🔗 https://crud-usuarios-render-hj5j.onrender.com/usuarios


---

# ⚙️ Tecnologías Utilizadas

## Frontend

- HTML5
- CSS3

## Backend

- Node.js
- Express.js

## Base de Datos

- PostgreSQL
- Render PostgreSQL Database

## Librerías utilizadas

- `pg` → conexión con PostgreSQL
- `cors` → manejo de solicitudes externas
- `dotenv` → gestión de variables de entorno

## Herramientas DevOps

- Git
- GitHub
- Render Cloud Platform
- Thunder Client / Postman


---

# 🚀 Ejecución del Proyecto en Local

## 1. Clonar repositorio

```bash
git clone https://github.com/anngiepp/crud-usuarios-render.git
```

---

## 2. Ingresar al proyecto

```bash
cd crud-usuarios-render
```

---

## 3. Instalar dependencias

```bash
npm install
```

---

## 4. Configurar variables de entorno

Crear un archivo `.env`:

```env
DATABASE_URL=postgresql://usuario:password@localhost:5432/usuarios
PORT=3000
```

La aplicación utiliza la variable `DATABASE_URL` para conectarse tanto a PostgreSQL local como a PostgreSQL desplegado en Render.

---

## 5. Ejecutar servidor

```bash
node server.js
```

Servidor disponible en:

```
http://localhost:3000
```


---

# 🌐 Endpoints Disponibles

## 👤 Usuarios API REST

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| GET | `/usuarios` | Obtiene todos los usuarios registrados |
| POST | `/usuarios` | Registra un nuevo usuario |
| DELETE | `/usuarios/:id` | Elimina un usuario mediante su ID |


---

# 📬 Ejemplo de Uso

## Crear Usuario

### POST `/usuarios`

Request:

```json
{
    "nombre": "Angie",
    "correo": "angie@gmail.com"
}
```

Respuesta:

```json
{
    "mensaje": "Usuario creado",
    "usuario": {
        "id": 1,
        "nombre": "Angie",
        "correo": "angie@gmail.com",
        "creado_en": "2026-08-26T17:40:11.927Z"
    }
}
```


---

# 📸 Evidencias del Funcionamiento


## 🌐 Despliegue del Perfil HTML en Render (Static Site)

Página estática desplegada correctamente mediante Render.

![Perfil desplegado en Render](./img/img1.png)


---

## ⚙️ Configuración del Proyecto Backend Node.js

Estructura del backend y configuración del servicio.

![Configuración Backend](./img/img2.png)


---

## 📂 Repositorio CRUD Usuarios en GitHub

Código fuente almacenado y versionado mediante GitHub.

![Repositorio GitHub](./img/img3.png)


---

# ☁️ Base de Datos y Servicios Cloud


## 🗄️ Instancia PostgreSQL en Render

Base de datos PostgreSQL creada y administrada desde la plataforma Render.

![PostgreSQL Render](./img/img4.png)


---

## 🚀 Web Service Backend desplegado

Servicio backend ejecutándose correctamente en Render.

![Web Service Render](./img/img5.png)


---

# 📦 Pruebas de Endpoints CRUD


## 🔍 GET `/usuarios`

Consulta inicial de usuarios registrados en PostgreSQL.

![GET Usuarios](./img/img6.png)


---

## ➕ POST `/usuarios`

Creación exitosa de un nuevo usuario mediante la API REST.

![POST Usuario](./img/img7.png)


---

# ✨ Arquitectura Cloud Seleccionada

La arquitectura implementada utiliza los servicios administrados de Render:

```
Usuario
   |
   |
Static Site Render
   |
   |
API REST Node.js + Express
   |
   |
PostgreSQL Render Database
```


Se seleccionó **PostgreSQL** debido a su compatibilidad con la infraestructura PaaS de Render y la facilidad de integración mediante variables de entorno.

El backend realiza la creación automática de la estructura de datos mediante:

```sql
CREATE TABLE IF NOT EXISTS usuarios
```

permitiendo que la aplicación pueda inicializar correctamente el modelo de datos durante el despliegue.


---

# 🔐 Gestión de Configuración

Las credenciales de conexión y configuraciones sensibles no se almacenan directamente en el código fuente.

Se utilizan variables de entorno mediante:

```
.env
```

permitiendo una implementación más segura y siguiendo buenas prácticas de desarrollo cloud.


---

# ✩⋆ ✮ Conclusión

Se logró desplegar correctamente una aplicación web estática y una API RESTful conectada a una base de datos relacional en la nube utilizando la plataforma **Render**.

La integración entre GitHub y Render permitió automatizar el proceso de despliegue, facilitando la administración de versiones, actualización del servicio y gestión eficiente de recursos cloud.

El proyecto demuestra la aplicación práctica de una arquitectura PaaS moderna utilizando servicios administrados, integración continua y desarrollo backend orientado a la nube.