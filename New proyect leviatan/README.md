#  LEVIATAN FRONTEND

Frontend desarrollado con **React + Vite + TypeScript**, utilizando la arquitectura **Feature Folder Structure**, una organización moderna orientada a aplicaciones escalables y mantenibles.

---

#  Arquitectura: Feature Folder Structure

Este proyecto organiza el código por **funcionalidades del sistema (features)** en lugar de organizarlo por tipo de archivo.

✅ Cada módulo contiene su propia lógica
✅ Separación clara de responsabilidades
✅ Escalable para proyectos grandes
✅ Fácil mantenimiento y trabajo en equipo

---

# 📂 Estructura del Proyecto

```
src/
│
├── app/                     # configuración global de la aplicación
│   ├── App.tsx
│   ├── main.tsx
│   └── routes/
│       ├── ProtectedRoute.tsx
│       ├── PublicRoute.tsx
│       └── RootRedirect.tsx
│
├── features/                # módulos funcionales del sistema
│
│   ├── auth/
│   │   └── pages/
│   │        └── Login.tsx
│
│   ├── landing/
│   │   ├── pages/
│   │   │    └── Landing.tsx
│   │   └── components/
│   │        ├── Button.tsx
│   │        ├── Call_Action.tsx
│   │        ├── Features_Section.tsx
│   │        ├── Header.tsx
│   │        ├── Hero_Section.tsx
│   │        ├── How_Works_Section.tsx
│   │        └── Testimonials.tsx
│
│   └── application/
│        ├── profile/
│        │    ├── profileEdit.tsx
│        │    └── profileChangePass.tsx
│        │
│        ├── statistics_user/
│        │    └── statistics_user.tsx
│        │
│        ├── upload_document/
│        │    └── Upload_Document.tsx
│        │
│        ├── view_document/
│        │    ├── chat/
│        │    ├── PDF/
│        │    └── QUIZ/
│        │
│        └── view_subject/
│
├── shared/                  # elementos reutilizables globalmente
│   ├── components/
│   ├── interfaces/
│   ├── layout/
│   │    └── Layout.tsx
│   └── utils/
│
├── styles/
│   ├── App.css
│   └── index.css
│
└── assets/                  # imágenes, iconos y recursos estáticos
```

---

#  Explicación por Carpetas

---

##  `app/` — Configuración Global

Contiene el punto central de ejecución de la aplicación.

### `main.tsx`

* Punto de entrada de React.
* Renderiza la aplicación en el DOM.

### `App.tsx`

* Componente raíz.
* Define estructura general y conexión con rutas.

### `routes/`

Controla la navegación y acceso a páginas.

* **ProtectedRoute.tsx**

  * Permite acceso solo a usuarios autenticados.

* **PublicRoute.tsx**

  * Restringe acceso a páginas públicas cuando el usuario ya inició sesión.

* **RootRedirect.tsx**

  * Redirección automática según estado del usuario.

 Importante: las rutas usan la autenticación, pero no contienen su lógica.

---

##  `features/` — Módulos del Sistema

Cada carpeta representa una funcionalidad independiente.

---

###  `features/auth`

Gestiona la autenticación del usuario.

#### `pages/Login.tsx`

* Pantalla de inicio de sesión.
* Entrada al sistema.

Responsabilidades:

* Login de usuario
* Validación inicial
* Inicio de sesión

---

###  `features/landing`

Contiene la página pública principal.

#### `pages/Landing.tsx`

Página inicial del sistema.

#### `components/`

Componentes exclusivos del landing:

* **Header.tsx** → navegación superior
* **Hero_Section.tsx** → sección principal visual
* **Features_Section.tsx** → características del sistema
* **How_Works_Section.tsx** → explicación del funcionamiento
* **Testimonials.tsx** → opiniones de usuarios
* **Call_Action.tsx** → llamada a la acción
* **Button.tsx** → botón reutilizable dentro del landing

 Estos componentes solo pertenecen al landing.

---

###  `features/application`

Área privada del sistema (dashboard).

#### `profile/`

Gestión del perfil del usuario.

* `profileEdit.tsx` → editar información
* `profileChangePass.tsx` → cambiar contraseña

---

#### `statistics_user/`

* `statistics_user.tsx`
* Visualización de estadísticas del usuario.

---

#### `upload_document/`

* `Upload_Document.tsx`
* Subida de documentos al sistema.

---

#### `view_document/`

Visualización e interacción con documentos.

Submódulos:

* `chat/` → interacción o mensajería
* `PDF/` → visor de documentos PDF
* `QUIZ/` → evaluaciones relacionadas

---

#### `view_subject/`

Gestión o visualización de materias o contenidos.

---

##  `shared/` — Código Reutilizable

Elementos usados por múltiples features.

### `components/`

Componentes globales como:

* Navbar
* Sidebar
* Footer
* Popups

---

### `layout/Layout.tsx`

Estructura visual general del dashboard:

* Sidebar
* Navbar
* Contenido dinámico

---

### `utils/`

Funciones auxiliares y configuraciones.

---

### `interfaces/`

Interfaces TypeScript compartidas.

---

##  `styles/`

Estilos globales.

* `index.css` → estilos base
* `App.css` → estilos generales de la aplicación

---

##  `assets/`

Recursos estáticos:

* imágenes
* iconos
* fuentes

---

#  Flujo Arquitectónico

```
Routes (app)
      ↓
Feature (business logic)
      ↓
Components
      ↓
Shared UI / Utils
```

---

#  Beneficios de esta Arquitectura

* Escalable
* Modular
* Fácil mantenimiento
* Separación clara de responsabilidades
* Preparada para crecimiento empresarial

---

#  Reglas del Proyecto

* Funcionalidades → `features/`
* Componentes globales → `shared/`
* Configuración → `app/`
* Evitar dependencias entre features
* Mantener cada módulo independiente

---

#  Tecnologías

* React
* Vite
* TypeScript
* React Router
* Framer Motion
* CSS

---

# Objetivo

Mantener una arquitectura limpia y profesional que permita agregar nuevas funcionalidades sin afectar el resto del sistema.

Ejemplo:

```
features/
 └── new-feature/
```

---

 Proyecto estructurado siguiendo prácticas modernas de arquitectura frontend profesional.
