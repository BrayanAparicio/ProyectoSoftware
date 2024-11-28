# README para el Proyecto Parqueadero

Este documento te guiará a través del proceso de configuración y ejecución del proyecto de parqueadero desde cero.

## Requisitos Previos
Antes de comenzar, asegúrate de tener instalados los siguientes programas en tu máquina:

- **Node.js** (versión 14 o superior): [Descargar Node.js](https://nodejs.org/)
- **npm** (que se instala automáticamente con Node.js)
- **SQLite** (para la base de datos): [Descargar SQLite](https://www.sqlite.org/download.html)

## Descarga el proyecto
Descarga el archivo .zip y descomprimelo en la ruta que desees

## Instalación de Dependencias
Una vez dentro de la carpeta del proyecto, instala las dependencias necesarias utilizando npm:

```bash
npm install
```
Esto instalará todas las bibliotecas necesarias que se encuentran en el archivo package.json.

## Configuración de la Base de Datos
El proyecto utiliza SQLite como base de datos. La configuración inicial de la base de datos se realiza automáticamente al ejecutar el archivo database.js. Asegúrate de que el archivo parqueadero.db se cree en la raíz del proyecto.

Para inicializar la base de datos, ejecuta:

```bash
node database.js
```
Esto creará las tablas necesarias (vehiculos, usuarios, reservas, facturas) en la base de datos.

## Ejecución del Proyecto
Para iniciar el servidor, ejecuta el siguiente comando en la terminal:

```bash
node app.js
```
El servidor se ejecutará en http://localhost:3000. Puedes abrir un navegador y dirigirte a esa dirección para acceder a la aplicación.

## Estructura del Proyecto
La estructura del proyecto es la siguiente:

parqueadero/
│
├── app.js              # Archivo principal de la aplicación
├── database.js         # Configuración de la base de datos
├── public/             # Archivos estáticos (CSS, imágenes, etc.)
│   └── styles.css      # Estilos CSS de la aplicación
├── views/              # Plantillas EJS para las vistas
├── package.json        # Archivo de configuración de npm
└── ...

## Rutas Principales
/registro: Página para registrar un nuevo usuario.
/login: Página de inicio de sesión.
/: Página principal que muestra los vehículos en parqueadero.
/admin: Panel de administración para gestionar vehículos y reservas.
/reservar: Página para realizar una nueva reserva.

El usuario de tipo administrador solo podra ser registrado por el programador,
y tendra acceso a todas las rutas.

Para registrar el administrador se puede directamente en la base de datos o modificando el formulario de registro para que este se registre, en caso de ser la segunda opcion hay que colocar el siguiente codigo en la vista de registro
<option value="admin">Administrador</option>, el codigo iria el la linea 25 de registro.ejs
