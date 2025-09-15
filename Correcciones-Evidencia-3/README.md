#  Sistema de Automatización de Hogar - ABP Programador

## 📋 Descripción del Proyecto

Sistema de automatización domótica desarrollado en Python que permite gestionar dispositivos inteligentes y ejecutar automatizaciones en múltiples hogares.

###  CORRECCIONES IMPLEMENTADAS

#### Correcciones solicitadas por profesores:
1. **Formato de inputs**: Agregados espacios y dos puntos para mejor legibilidad
2. **Documentación EV2**: Creada documentación completa de automatizaciones
3. **Coherencia modelo relacional**: Actualizada estructura según nueva base de datos
4. **Prefijos en confirmaciones**: Agregados prefijos para documentar historia del fuente

#### 🔧 Mejoras técnicas implementadas:
- Campos actualizados: `id_rol` → `role_id`, `nombre` → `name`, `activa` → `active`
- Estructura de BD coherente con diagrama relacional
- Prefijos informativos: `[AUTOMATION-SUCCESS]`, `[ACCESS-DENIED]`, etc.
- Documentación técnica de automatizaciones

## 🗄️ Estructura del Proyecto

```
abp-programador/
├── controllers/           # Lógica de negocio
│   ├── automation_controller.py
│   ├── devices_controller.py
│   └── user_controller.py
├── model/                # Modelos de datos
│   ├── automaions_data.py     # Automatizaciones
│   ├── device_automation_data.py  # Relación dispositivo-automatización
│   ├── devices_data.py        # Dispositivos
│   ├── event_data.py          # Registro de eventos
│   ├── home.py               # Hogares
│   ├── locations_data.py     # Ubicaciones
│   ├── rol.py               # Roles de usuario
│   ├── states_data.py       # Estados de dispositivos
│   ├── types_data.py        # Tipos de dispositivos
│   ├── user.py              # Usuarios
│   └── user_home_data.py    # Relación usuario-hogar
├── view/                 # Interfaces de usuario
│   ├── devices_view.py
│   └── users_view.py
├── utils/               # Utilidades
│   ├── devices_utils.py
│   └── helpers.py
├── main.py              # Punto de entrada
├── DOCUMENTACION_AUTOMATIZACIONES.md  # 📋 Nueva documentación EV2
└── README.md
```

##  Características Principales

### Sistema de Usuarios
- **Administradores**: Acceso completo a todas las funcionalidades
- **Usuarios estándar**: Acceso a automatizaciones de sus hogares asignados
- Autenticación por email y contraseña

### Gestión de Hogares
- Soporte para múltiples hogares por usuario
- Casa Principal y Casa de Campo predefinidas
- Relación muchos-a-muchos usuario-hogar

### Dispositivos Inteligentes
- **Tipos soportados**: Luces, Termostatos, Ventiladores, Cámaras, Electrodomésticos
- **Estados**: Encendido/Apagado con IDs relacionales
- **Ubicaciones**: Sala, Cocina, Dormitorio, etc.
- Características detalladas por tipo de dispositivo

### Automatizaciones
1. **Encender luces del salón** - Casa Principal
2. **Apagar todas las luces** - Casa Principal  
3. **Encender luz de oficina** - Casa de Campo

### Registro de Eventos
- Log automático de todas las acciones
- Timestamps y fuente de origen
- Trazabilidad completa del sistema

## Uso del Sistema

### Instalación
```bash
git clone [repository-url]
cd abp-programador
python main.py
```

### Credenciales por defecto
- **Admin**: fernandomoyano21@gmail.com / admin123
- Los usuarios estándar se pueden registrar desde la aplicación

### Menús disponibles

####  Menú Administrador:
1. Consultar automatizaciones activas
2. Agregar dispositivo
3. Listar dispositivos
4. Buscar dispositivo
5. Eliminar dispositivo
6. Modificar rol de usuario

#### Menú Usuario:
1. Consultar datos personales
2. Ejecutar automatización
3. Listar dispositivos

## Modelo Relacional

El sistema implementa las siguientes tablas según diagrama:
- `role` - Roles de usuario
- `user` - Usuarios del sistema
- `home` - Hogares disponibles
- `user_home` - Relación usuario-hogar
- `state` - Estados de dispositivos
- `location` - Ubicaciones físicas
- `device_type` - Tipos de dispositivos
- `device` - Dispositivos del sistema
- `automation` - Automatizaciones configuradas
- `device_automation` - Relación dispositivo-automatización
- `event` - Registro de eventos del sistema

##  Documentación Técnica

Consultar `DOCUMENTACION_AUTOMATIZACIONES.md` para:
- Detalles técnicos de cada automatización
- Estructura de datos completa
- Flujo de ejecución
- Consideraciones de seguridad y acceso
- Guía de extensibilidad

## Características de Calidad

### Prefijos de Confirmación
- `[AUTOMATION-SUCCESS]` - Automatización ejecutada correctamente
- `[AUTOMATION-ERROR]` - Error en ejecución de automatización
- `[ACCESS-DENIED]` - Acceso denegado a recurso
- `[INPUT-ERROR]` - Error en entrada de datos
- `[USER-INFO]` - Información para el usuario

### Seguridad
- Validación de acceso por hogar
- Separación de roles administrador/usuario
- Autenticación requerida
- Logs de auditoría

---

**Desarrollador**: Fernando Moyano, Santiago Ortega, Rafael Perazzolo  
**Versión**: 2.0 (Corregida - Enero 2025)  
**Institución**: ISPC  
**Materia**: ABP - Programador