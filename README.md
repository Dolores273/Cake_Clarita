# 🧁 Clarita Cakes - Sistema de Gestión de Pastelería

**Clarita Cakes** es una solución Full-Stack moderna diseñada para digitalizar el flujo de trabajo de una pastelería artesanal. El sistema permite la administración total del inventario y ofrece a los clientes una experiencia de compra fluida y segura.

---

## 📑 Tabla de Contenidos

1. [Resumen del Proyecto](#resumen-del-proyecto)
2. [Arquitectura de Roles](#arquitectura-de-roles)
3. [Tecnologías Utilizadas](#tecnologías-utilizadas)
4. [Configuración de la Base de Datos](#configuración-de-la-base-de-datos)
5. [Instalación y Puesta en Marcha](#instalación-y-puesta-en-marcha)
6. [Diseño y Experiencia de Usuario](#diseño-y-experiencia-de-usuario)

---

## 🌟 Resumen del Proyecto

El sistema aborda dos necesidades críticas:

* **Eficiencia Administrativa:** Automatiza el control de stock y la recepción de pedidos.
* **Experiencia del Cliente:** Facilita la visualización de productos y la realización de pedidos mediante formularios dinámicos.

---

## 👥 Arquitectura de Roles

### 👑 Panel de Administración (Perfil: Clarita)

Diseñado para la gestión operativa del negocio:

* **Gestión de Inventario (CRUD):** Control total sobre el catálogo (Crear, Editar, Eliminar productos).
* **Monitoreo de Stock:** Visualización en tiempo real de porciones y pasteles enteros disponibles.
* **Gestión de Pedidos:** Tabla centralizada para aceptar o rechazar pedidos, con visualización de datos sensibles del cliente.
* **Sincronización Automática:** Al aceptar un pedido, el sistema descuenta automáticamente las unidades del inventario.

### 🍪 Panel de Cliente (Perfil: Dolores)

Enfocado en la conversión y facilidad de uso:

* **Catálogo Interactivo:** Galería de productos con precios actualizados y descripciones.
* **Sistema de Compra Modal:** Formulario emergente que captura la información necesaria para la entrega sin recargar la página.
* **Validación de Disponibilidad:** El sistema restringe compras si el producto está agotado.

---

## 🛠 Tecnologías Utilizadas

| Capa | Tecnología |
| --- | --- |
| **Frontend** | React.js (Hooks, Context, CSS Moderno) |
| **Backend** | Node.js & Express.js |
| **Base de Datos** | MySQL / MariaDB |
| **Autenticación** | JSON Web Tokens (JWT) para sesiones |
| **Comunicación** | API RESTful (Fetch API) |

---

## 🗄 Configuración de la Base de Datos

Ejecuta los siguientes scripts en tu terminal de MySQL o mariadb a través de phpMyAdmin para configurar el entorno de datos:

```sql
CREATE DATABASE fastech_db;
USE fastech_db;

-- 1. Tabla de Usuarios
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    rol ENUM('admin', 'cliente') NOT NULL
);

-- 2. Tabla de Productos
CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL DEFAULT 0, -- Porciones
    pasteles_disponibles INT NOT NULL DEFAULT 0, -- Pasteles enteros
    imagen_url TEXT
);

-- 3. Tabla de Pedidos
CREATE TABLE pedidos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre_cliente VARCHAR(100) NOT NULL,
    apellido_cliente VARCHAR(100) NOT NULL,
    dui VARCHAR(20),
    telefono VARCHAR(15) NOT NULL,
    direccion TEXT,
    fecha_entrega DATETIME NOT NULL,
    producto_id INT,
    cantidad INT NOT NULL DEFAULT 1,
    tipo_pedido VARCHAR(50),
    estado VARCHAR(20) DEFAULT 'Pendiente',
    FOREIGN KEY (producto_id) REFERENCES productos(id) ON DELETE CASCADE
);

-- Datos Iniciales
INSERT INTO usuarios (username, password, rol) VALUES ('Clarita', '12345', 'admin');
INSERT INTO usuarios (username, password, rol) VALUES ('Dolores', '2008', 'cliente');

```

---

## 🚀 Instalación y Puesta en Marcha

### 1. Clonar y Preparar

```bash
git clone https://github.com/tu-usuario/clarita-cakes.git
cd clarita-cakes

```

### 2. Iniciar el Backend

```bash
# Entrar a la carpeta del servidor
cd backend
npm install
node server.js

```

### 3. Iniciar el Frontend

```bash
# En una nueva terminal, desde la raíz del proyecto
npm install
npm start

```

---

## 🎨 Diseño y Experiencia de Usuario

El diseño visual ha sido cuidadosamente seleccionado para evocar la calidez de una repostería profesional:

* **Paleta de Colores:** Uso de tonos `#d81b60` (rosa fuerte) para llamados a la acción, `#ffd1dc` (rosa pastel) para fondos y tonos madera para tipografía.
* **Responsividad:** La interfaz se adapta a dispositivos móviles para permitir pedidos desde smartphones.
* **Feedback Visual:** Alertas personalizadas y cambios de estado dinámicos en los botones de gestión.

---

## 👤 Autor

* **Clarita** - *Desarrollo Inicial y Concepto*
* **Propósito:** Proyecto educativo para la gestión avanzada de bases de datos y desarrollo de aplicaciones web full-stack.

---

**¿Listo para probar Clarita Cakes?** Inicia sesión como `Clarita` para gestionar o como `Dolores` para endulzar tu día. 🍰

<img width="1855" height="1080" alt="Captura desde 2026-05-18 22-32-37" src="https://github.com/user-attachments/assets/43ed673d-3445-494e-805a-22962e1a4277" />

<img width="1855" height="1080" alt="Captura desde 2026-05-18 22-32-55" src="https://github.com/user-attachments/assets/dc1c05de-0e76-4830-851b-ee629b5a4fb6" />

<img width="1855" height="1080" alt="Captura desde 2026-05-18 22-33-02" src="https://github.com/user-attachments/assets/cdbb00c7-6593-446d-87e4-3dfbbef86c95" />

<img width="682" height="338" alt="Captura desde 2026-05-18 22-35-04" src="https://github.com/user-attachments/assets/27348b99-5647-4eb7-8308-4c484ba6c4a6" />

<img width="1842" height="994" alt="Captura desde 2026-05-18 22-35-22" src="https://github.com/user-attachments/assets/6787f6e7-5122-4b95-a069-9b137fc93c09" />

<img width="1920" height="1200" alt="Captura desde 2026-05-19 22-04-42" src="https://github.com/user-attachments/assets/475771bf-9770-4da0-9c9f-3e286a0eb015" />


