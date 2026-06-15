# SafePlace — Frontend

Aplicación web para el sistema de monitoreo biométrico SafePlace. Permite gestionar trabajadores, visualizar alertas en tiempo real y configurar umbrales del sistema según el rol del usuario.

## Stack

- **HTML5 + CSS3 + JavaScript** vanilla
- **Chart.js** para gráficos de biométrica
- Sin framework ni bundler — archivos estáticos servidos directamente

## Páginas

| Archivo | Rol | Descripción |
|---------|-----|-------------|
| `InicioSesion.html` | Todos | Login con autenticación JWT |
| `Admin-Home.html` | Admin | Dashboard con KPIs y gráficos |
| `Admin-Empleados.html` | Admin | CRUD de trabajadores |
| `Admin-Configuración.html` | Admin | Umbrales biométricos |
| `Admin-RolesPermisos.html` | Admin | Gestión de roles |
| `Supervisor-Home.html` | Supervisor | Dashboard del supervisor |
| `Supervisor-Monitoreo.html` | Supervisor | Monitoreo en tiempo real |

## Correr en local

```bash
# Clonar el repo
git clone https://github.com/mackhood/safeplace-frontend.git
cd safeplace-frontend

# Instalar dependencias (solo vite para dev server)
npm install

# Levantar servidor de desarrollo
npm run dev
```

Abrí `http://localhost:5173/InicioSesion.html` en el browser.

## Usuarios de prueba

| Usuario | Contraseña | Rol |
|---------|-----------|-----|
| `admin` | `admin123` | Administrador |
| `supervisor` | `super123` | Supervisor |
| `seguridad` | `seg123` | Seguridad |

## Conexión con el backend

La URL del backend está definida en cada archivo JS como:

```js
const API_URL = 'https://safeplace-backend.onrender.com/api/v1';
```

Para apuntar a un backend local cambiá esa constante a `http://localhost:8000/api/v1`.

## Deploy en Vercel

El frontend está deployado en [Vercel](https://vercel.com) con deploy automático en cada push a `main`.

**URL de producción:** `https://safeplace-frontend-ofw3-five.vercel.app`

**Configuración en Vercel:**

| Campo | Valor |
|-------|-------|
| Framework Preset | Other |
| Build Command | *(vacío)* |
| Output Directory | `.` |

El archivo `vercel.json` incluido en el repo maneja el ruteo — la raíz `/` redirige automáticamente a `InicioSesion.html`.

> Vercel redeploya automáticamente con cada push a `main`. No se necesitan variables de entorno.
