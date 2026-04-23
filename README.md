# Analisis-y-diseno-de-sistemas-TATIANA-CABRERA-23022026_C12_202631-
Analisis y diseño de sistemas ibero

# SaludYa - Sistema de Gestión de Citas Médicas 

# 🏥 SaludYa — Sistema de Gestión de Citas Médicas

> Aplicación web para la gestión eficiente de citas médicas en consultorios independientes y centros de atención de pequeña escala en Colombia.

---

## 📋 Tabla de Contenido

- [Descripción](#descripción)
- [Stack Tecnológico](#stack-tecnológico)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Requisitos Previos](#requisitos-previos)
- [Instalación y Configuración](#instalación-y-configuración)
- [Variables de Entorno](#variables-de-entorno)
- [Ramas y Flujo de Trabajo](#ramas-y-flujo-de-trabajo)
- [Equipo](#equipo)
- [Documentación](#documentación)

---

## 📌 Descripción

**SaludYa** permite a los pacientes reservar, cancelar y reprogramar citas médicas de manera autónoma, y al personal médico gestionar su agenda de forma eficiente, reduciendo los errores operativos en consultorios de pequeña escala.

### Funcionalidades del MVP

- ✅ Registro e inicio de sesión de pacientes y médicos con roles diferenciados
- ✅ Búsqueda de médicos por especialidad y visualización de disponibilidad
- ✅ Reserva, cancelación y reprogramación de citas
- ✅ Configuración de agenda por parte del médico
- ✅ Notificación automática por correo 24 horas antes de la cita
- ✅ Historial de citas pasadas y futuras para el paciente

---

## 🛠️ Stack Tecnológico

| Capa | Tecnología |
|---|---|
| Frontend | React.js + Tailwind CSS |
| Backend | Node.js + Express.js |
| Base de datos | PostgreSQL (Neon / Supabase) |
| Autenticación | JWT + bcrypt |
| Correo | Nodemailer + SMTP |
| Control de versiones | Git + GitHub |
| Despliegue | Render / Railway (plan gratuito) |
| Diseño | Figma |

---

## 📁 Estructura del Proyecto

```
saludya/
├── frontend/                  # React.js + Tailwind CSS
│   ├── public/
│   └── src/
│       ├── assets/            # Imágenes, íconos, fuentes
│       ├── components/        # Componentes reutilizables
│       ├── pages/             # Login, Dashboard, Citas, etc.
│       ├── services/          # Llamadas a la API REST
│       ├── context/           # AuthContext (manejo de JWT)
│       └── hooks/             # Custom hooks
│
├── backend/                   # Node.js + Express
│   ├── src/
│   │   ├── controllers/       # Lógica de negocio por módulo
│   │   ├── routes/            # Definición de rutas API REST
│   │   ├── models/            # Modelos y queries PostgreSQL
│   │   ├── middlewares/       # Autenticación JWT, validaciones
│   │   └── services/          # Nodemailer, utilidades
│   └── .env.example           # Plantilla de variables de entorno
│
├── docs/                      # Documentación académica
│   ├── actividad-1.pdf
│   ├── actividad-2.pdf
│   ├── wireframes/
│   └── diagramas/
│
├── .gitignore
└── README.md
```

---

## ✅ Requisitos Previos

Antes de instalar el proyecto, asegúrate de tener:

- [Node.js](https://nodejs.org/) v18 o superior
- [npm](https://www.npmjs.com/) v9 o superior
- [Git](https://git-scm.com/)
- Una base de datos PostgreSQL activa (puedes usar [Neon](https://neon.tech) o [Supabase](https://supabase.com) gratis)

---

## ⚙️ Instalación y Configuración

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/saludya.git
cd saludya
```

### 2. Configurar el Backend

```bash
cd backend
npm install
cp .env.example .env
# Edita el archivo .env con tus credenciales
npm run dev
```

### 3. Configurar el Frontend

```bash
cd frontend
npm install
npm run dev
```

El frontend estará disponible en `http://localhost:5173`  
El backend estará disponible en `http://localhost:3000`

---

## 🔐 Variables de Entorno

Copia el archivo `backend/.env.example` como `backend/.env` y completa los valores:

```env
# Servidor
PORT=3000

# Base de datos
DATABASE_URL=postgresql://usuario:contraseña@host/saludya

# JWT
JWT_SECRET=tu_clave_secreta_aqui
JWT_EXPIRES_IN=24h

# Correo (Nodemailer)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=tu_correo@gmail.com
SMTP_PASS=tu_contraseña_de_aplicacion
```

> ⚠️ **Nunca subas el archivo `.env` al repositorio.** Ya está incluido en el `.gitignore`.

---

## 🌿 Ramas y Flujo de Trabajo

### Ramas principales

| Rama | Propósito |
|---|---|
| `main` | Versión estable / entregables finales |
| `develop` | Integración general del equipo |
| `sprint-1/auth` | HU-01 a HU-04 — Autenticación y perfiles |
| `sprint-2/agenda` | HU-05 a HU-10 — Agenda y reservas |
| `sprint-3/notificaciones` | HU-11, HU-12 — Notificaciones e historial |

### Ramas por integrante

```
feature/alejandro-registro-usuario
feature/daniel-login-jwt
feature/cristian-agenda-medico
feature/julian-busqueda-medicos
```

### Convención de commits

```
feat: agregar formulario de registro de paciente
fix: corregir validación de correo duplicado
docs: actualizar README con instrucciones de instalación
test: agregar prueba unitaria para reserva de cita
style: ajustar estilos del dashboard
refactor: reorganizar controlador de citas
```

### Flujo de trabajo

1. Crea tu rama desde `develop`: `git checkout -b feature/tu-nombre-modulo`
2. Desarrolla y haz commits con la convención definida
3. Abre un **Pull Request** hacia `develop`
4. Espera la revisión de al menos **1 compañero** antes de mergear
5. Solo el Product Owner mergea hacia `main`

---

## 👥 Equipo

| Nombre | Rol Scrum | Módulo principal |
|---|---|---|
| Alejandro Mora Alvarez | Product Owner | Frontend Auth, coordinación |
| Daniel Alejandro González Arévalo | Scrum Master | Backend Auth, JWT |
| Cristian Steven Abril Aldana | Developer | Base de datos, Agenda médica |
| Julian Vega Joya | Developer | Búsqueda de médicos, Wireframes |

---

## 📚 Documentación

- 📄 [Actividad 1 — Formulación del proyecto](./docs/actividad-1.pdf)
- 🎨 [Figma — Diseño UI/UX](https://www.figma.com) *(agregar link del equipo)*
- 🗺️ [User Flow — Miro](https://miro.com/app/board/uXjVGodGduw=/)
- 📊 [Diagrama de Flujo](https://drive.google.com/file/d/1-T9MPkakgQmY7DNeaGScaPyOuGS6irx/view)

---

## 📝 Licencia

Proyecto académico — Corporación Universitaria Iberoamericana  
Facultad de Ingeniería — Ingeniería de Software  
Análisis y Diseño de Sistemas — Docente: Tatiana Cabrera  
Bogotá D.C., 2026







