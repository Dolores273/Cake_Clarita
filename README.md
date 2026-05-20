🧁 Clarita Cakes - Sistema de Gestión de Pastelería
¡Bienvenido a Clarita Cakes! Una aplicación web full-stack diseñada para gestionar el inventario de una pastelería y permitir a los clientes realizar pedidos personalizados en tiempo real.

Funcionalidades
El sistema cuenta con un control de acceso basado en roles para dos perfiles específicos:

Panel de Administración (Clarita)
Gestión de Inventario (CRUD): Crear, leer, actualizar y eliminar pasteles del catálogo.

Control de Stock: Visualización en tiempo real de las unidades disponibles.

Registro de Pedidos: Una tabla exclusiva donde Clarita puede ver los datos de los clientes (Nombre, DUI, Dirección) y qué pastel han solicitado.

Interfaz Intuitiva: Formulario vertical para añadir o editar productos con URL de imágenes.

Panel de Cliente (Dolores)
Catálogo Interactivo: Visualización de los pasteles disponibles con sus respectivos precios y fotos.

Sistema de Compras: Formulario dinámico (Modal) para realizar pedidos.

Validación de Stock: El sistema impide comprar productos agotados y actualiza el inventario automáticamente tras cada compra.

Tecnologías Utilizadas
Este proyecto utiliza el stack PERN (adaptado con MySQL):

Frontend: React.js, CSS3 (Diseño responsivo y animaciones).

Backend: Node.js, Express.js.

Base de Datos: MySQL.

Autenticación: JSON Web Tokens (JWT) para sesiones seguras.

Comunicación: API RESTful.

Requisitos Previos
Antes de comenzar, asegúrate de tener instalado:

Node.js (v14 o superior)

Instalación y Configuración
Clonar el repositorio

git clone https://github.com/tu-usuario/clarita-cakes.git
cd clarita-cakes

Configurar la Base de Datos
Crea una base de datos llamada fastech_db y ejecuta los siguientes scripts SQL:
-- Tabla de Usuarios
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    rol ENUM('admin', 'cliente') NOT NULL
);

-- Tabla de Productos
CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL,
    imagen_url TEXT
);

-- Tabla de Pedidos
CREATE TABLE pedidos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre_cliente VARCHAR(100),
    apellido_cliente VARCHAR(100),
    dui VARCHAR(20),
    direccion TEXT,
    producto_id INT,
    fecha_pedido TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (producto_id) REFERENCES productos(id)
);

-- Usuarios por defecto
INSERT INTO usuarios (username, password, rol) VALUES ('Clarita', '12345', 'admin');
INSERT INTO usuarios (username, password, rol) VALUES ('Dolores', '2008', 'cliente');

Configurar el Backend
Entra en la carpeta del servidor e instala las dependencias:

Bash
cd backend
npm install
node server.js

Configurar el Frontend
En otra terminal, entra en la carpeta del proyecto React:

npm install
npm start

Diseño Visual
El proyecto cuenta con una estética inspirada en repostería:

Colores: Paleta de rosas (#ffd1dc), chocolates (#5d4037) y cremas.

Componentes: Tarjetas modernas para los productos y ventanas modales desenfocadas para los formularios de compra.

Autor
Clarita

Propósito: Proyecto educativo para gestión de bases de datos y desarrollo web.

<img width="1855" height="1080" alt="Captura desde 2026-05-18 22-32-37" src="https://github.com/user-attachments/assets/43ed673d-3445-494e-805a-22962e1a4277" />

<img width="1855" height="1080" alt="Captura desde 2026-05-18 22-32-55" src="https://github.com/user-attachments/assets/dc1c05de-0e76-4830-851b-ee629b5a4fb6" />

<img width="1855" height="1080" alt="Captura desde 2026-05-18 22-33-02" src="https://github.com/user-attachments/assets/cdbb00c7-6593-446d-87e4-3dfbbef86c95" />

<img width="682" height="338" alt="Captura desde 2026-05-18 22-35-04" src="https://github.com/user-attachments/assets/27348b99-5647-4eb7-8308-4c484ba6c4a6" />

<img width="1842" height="994" alt="Captura desde 2026-05-18 22-35-22" src="https://github.com/user-attachments/assets/6787f6e7-5122-4b95-a069-9b137fc93c09" />

<img width="1920" height="1200" alt="Captura desde 2026-05-19 22-04-42" src="https://github.com/user-attachments/assets/475771bf-9770-4da0-9c9f-3e286a0eb015" />


