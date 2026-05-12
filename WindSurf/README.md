# Remote Jobs SaaS - Trabajos Remotos

Aplicación SaaS simple para buscar y publicar trabajos remotos. Sin base de datos, usando Node.js + Express en el backend y React estático en el frontend.

## Características

- **Backend**: Node.js con Express
- **Frontend**: React estático (cargado vía CDN)
- **Sin base de datos**: Datos almacenados en memoria
- **Simple**: Mínimas dependencias (solo Express)
- **Listo para Cloudways**: Configuración sencilla para despliegue

## Estructura del Proyecto

```
/
├── server.js          # Backend Node.js + Express
├── package.json       # Dependencias del proyecto
├── public/            # Frontend React estático
│   ├── index.html     # Página principal
│   ├── app.js         # Aplicación React
│   └── styles.css     # Estilos
└── README.md          # Este archivo
```

## Instalación Local

### 1. Instalar Node.js y npm

**Windows:**
- Descargar Node.js desde: https://nodejs.org/
- Instalar la versión LTS recomendada
- npm se instala automáticamente con Node.js

**Verificar instalación:**
```bash
node --version
npm --version
```

### 2. Instalar Dependencias

```bash
npm install
```

### 3. Ejecutar el Servidor

```bash
npm start
```

La aplicación estará disponible en: http://localhost:3000

## Uso de la Aplicación

### Ver Trabajos
- La página principal muestra todos los trabajos remotos disponibles
- Cada tarjeta muestra: título, empresa, descripción, salario, ubicación y tipo

### Aplicar a un Trabajo
- Click en "Aplicar Ahora" en cualquier trabajo
- Llenar el formulario con nombre, email y resumen/CV
- La aplicación se envía y se guarda en memoria

### Publicar un Nuevo Trabajo
- Click en "Publicar Trabajo" en el menú
- Llenar el formulario con los detalles del puesto
- El trabajo se agrega inmediatamente a la lista

## API Endpoints

### Trabajos
- `GET /api/jobs` - Listar todos los trabajos
- `GET /api/jobs/:id` - Obtener un trabajo específico
- `POST /api/jobs` - Crear un nuevo trabajo

### Aplicaciones
- `POST /api/apply` - Enviar una aplicación
- `GET /api/applications` - Listar todas las aplicaciones

## Despliegue en Cloudways

### Requisitos
- Cuenta en Cloudways
- Aplicación Node.js

### Pasos para Desplegar

1. **Subir el Código**
   - Subir todos los archivos del proyecto a tu servidor Cloudways
   - Puedes usar Git, FTP o el panel de Cloudways

2. **Configurar el Servidor**
   - En Cloudways, selecciona tu aplicación
   - Ve a "Settings" > "Application Settings"
   - Configura:
     - **Root Directory**: `/public` (para servir archivos estáticos)
     - **Startup Command**: `node server.js`
     - **Port**: 3000 (o el que prefieras)

3. **Instalar Dependencias**
   - Accede via SSH a tu servidor
   - Navega al directorio del proyecto
   - Ejecuta: `npm install`

4. **Iniciar la Aplicación**
   - Cloudways iniciará automáticamente la aplicación
   - O puedes iniciarla manualmente: `npm start`

5. **Configurar Dominio**
   - Agrega tu dominio en Cloudways
   - Configura SSL si es necesario

### Variables de Entorno (Opcional)

Puedes configurar el puerto usando variable de entorno:
```bash
export PORT=8080
npm start
```

## Notas Importantes

- **Sin persistencia**: Los datos se pierden al reiniciar el servidor (sin base de datos)
- **Producción**: Para producción, considera agregar una base de datos real
- **Escalabilidad**: Esta arquitectura es básica, ideal para MVP o prototipos

## Tecnologías

- **Backend**: Node.js, Express
- **Frontend**: React (vía CDN), Babel (para JSX)
- **Estilos**: CSS puro
- **Sin build tools**: React se ejecuta directamente en el navegador

## Licencia

Proyecto de código abierto para uso educativo y comercial.
