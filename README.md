# ERP Control de Obra (Módulo Base)

## 🚀 Descripción General
Este proyecto es el punto de partida para desarrollar un **ERP interno para la empresa de construcción**, comenzando con el módulo de **Control de Obra**.  
El objetivo principal es **registrar avances diarios desde obra**, vincularlos con **trabajos planificados**, **materiales utilizados**, y generar **indicadores de avance físico y desviaciones**.

El sistema se desarrollará con:
- **Backend:** Python + Django + Django REST Framework
- **Frontend:** React (integrado luego del MVP)
- **Base de datos:** PostgreSQL
- **Infraestructura:** entorno local, con vistas a despliegue en servidor interno o nube.

---

## 🧭 Roadmap General del ERP

1. **Usuarios y Roles**
   - Oficina, Capataz, Administrador.
   - Permisos y autenticación JWT.

2. **Módulo de Obras**
   - Creación de obras, ubicaciones, tareas esperadas.

3. **Parte Diario**
   - Registro de avances (m², m³, unidades, etc.).
   - Carga de materiales usados, comentarios y fotos.
   - Asociado a obra, ubicación y tarea.

4. **Materiales**
   - Catálogo base editable.
   - En el futuro: integración con módulo de compras y proveedores.

5. **Dashboard**
   - Avance físico vs planificado.
   - Desvíos de materiales previstos vs reales.
   - Análisis por obra y por período (certificaciones).

6. **Módulos Futuros**
   - Compras y proveedores (facturas/remitos).
   - Costos y certificaciones.
   - Planificación de obra.

---

## 🧩 Estructura Inicial del Proyecto

```
c2kerp/
│
├── manage.py
├── requirements.txt
├── .venv/
│
├── c2kerp/                  # Configuración del proyecto Django
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── apps/
│   ├── users/
│   ├── obras/
│   ├── partes/
│   └── materiales/
│
└── README.md
```

---

## 🧱 Etapas de Desarrollo

### **1️⃣ Etapa 1: Setup base del proyecto**
- Crear entorno virtual y proyecto Django.
- Configurar base de datos PostgreSQL.
- Crear estructura de apps (`users`, `obras`, `partes`, `materiales`).
- Configurar Django REST Framework.

### **2️⃣ Etapa 2: Autenticación y Roles**
- Modelo de usuario extendido.
- Roles: `Administrador`, `Oficina`, `Capataz`.
- Login con JWT y endpoints de registro.

### **3️⃣ Etapa 3: Módulo de Obras**
- Modelo `Obra` y `Ubicacion`.
- Carga de tareas planificadas.
- Endpoints para CRUD.

### **4️⃣ Etapa 4: Parte Diario**
- Modelo `ParteDiario`.
- Registro de avances, materiales usados, comentarios y fotos.
- Validaciones y control por usuario.

### **5️⃣ Etapa 5: Materiales**
- Modelo `Material` y relación con obras y partes diarios.
- Soporte para materiales nuevos desde obra.

### **6️⃣ Etapa 6: Dashboard básico**
- API con métricas de avance físico y materiales.
- Integración inicial con frontend React (opcional).

---

## 🧪 Casos de Uso Clave

1. **Capataz**
   - Inicia sesión → selecciona obra → registra parte diario → carga avance y materiales → sube fotos.
2. **Oficina**
   - Crea obras, ubicaciones y tareas planificadas.
   - Consulta dashboards y verifica avances.
3. **Administrador**
   - Gestiona usuarios, permisos y configuraciones globales.

---

## ⚙️ Tecnologías Recomendadas

| Componente | Herramienta | Descripción |
|-------------|-------------|--------------|
| Backend | Django + DRF | Framework principal para API REST |
| Frontend | React | Interfaz futura para la webapp |
| Base de datos | PostgreSQL | Relacional y escalable |
| Autenticación | JWT (SimpleJWT) | Tokens seguros |
| Librerías extra | Pillow, Django CORS, Django Environ | Imágenes, CORS, variables de entorno |

---

## 🧭 Próximo Paso

1. Confirmar la estructura de carpetas y entorno virtual.  
2. Crear el proyecto Django con:
   ```bash
   django-admin startproject c2kerp .
   ```
3. Crear la carpeta `apps/` y las apps iniciales:
   ```bash
   python manage.py startapp users
   python manage.py startapp obras
   python manage.py startapp partes
   python manage.py startapp materiales
   ```
