# GUÍA PARA EJECUTAR LOS TESTS DEL PROYECTO SMARTHOME

Este archivo contiene instrucciones paso a paso para ejecutar los tests usando pytest. Los tests están diseñados para principiantes en testing.

## REQUISITOS PREVIOS

1. Python 3.x instalado
2. pytest instalado (pip install pytest)

## ESTRUCTURA DE TESTS

```
tests/
├── test_role.py              # Tests para roles de usuario
├── test_state.py             # Tests para estados de dispositivos
├── test_location.py          # Tests para ubicaciones
├── test_device_type.py       # Tests para tipos de dispositivos
├── test_home.py              # Tests para hogares
├── test_user.py              # Tests para usuarios
├── test_device.py            # Tests para dispositivos
├── test_automation.py        # Tests para automatizaciones
├── test_event.py             # Tests para eventos del sistema
├── test_user_home.py         # Tests para relación usuario-hogar
└── test_device_automation.py # Tests para relación dispositivo-automatización
```

## COMANDOS PARA EJECUTAR TESTS

**Ejecutar todos los tests:**
```bash
pytest tests/
```

**Ejecutar un archivo específico:**
```bash
pytest tests/test_role.py
pytest tests/test_user.py
pytest tests/test_device.py
```

**Ejecutar un test específico:**
```bash
pytest tests/test_user.py::test_user_basico
pytest tests/test_device.py::TestDevice::test_crear_device_luz_sala
```

**Ejecutar tests con más información:**
```bash
pytest tests/ -v                    # Verbose (más detalles)
pytest tests/ -v -s                 # También muestra prints
pytest tests/ --tb=short            # Traceback corto en errores
```

**Ejecutar tests y ver cobertura:**
```bash
pytest tests/ --cov=models         # Requiere: pip install pytest-cov
```

## EJEMPLOS DE COMANDOS

```bash
# Ejecutar solo tests de las clases básicas
pytest tests/test_role.py tests/test_state.py tests/test_location.py

# Ejecutar tests de una clase específica
pytest tests/test_user.py::TestUser

# Ejecutar test específico con detalles
pytest tests/test_device.py::test_buscar_nombre_parcial -v -s
```

## INTERPRETANDO RESULTADOS

- **PASSED (.)** = Test exitoso
- **FAILED (F)** = Test falló
- **ERROR (E)** = Error en el test
- **SKIPPED (s)** = Test omitido

**Ejemplo de salida exitosa:**
```
tests/test_role.py::test_role_simple PASSED    [100%]
```

**Ejemplo de salida con error:**
```
tests/test_user.py::test_login_exitoso FAILED  [100%]
AssertionError: assert False == True
```

## ESTRUCTURA DE UN TEST TÍPICO

```python
def test_nombre_descriptivo():
    # Arrange (Preparar) - Crear datos de prueba
    objeto = ClaseATestear(parametros)
    
    # Act (Actuar) - Ejecutar la acción
    resultado = objeto.metodo_a_testear()
    
    # Assert (Afirmar) - Verificar resultado
    assert resultado == valor_esperado
```


## INSTALACIÓN DE DEPENDENCIAS

Si es la primera vez que usas pytest:

```bash
# Instalar pytest
pip install pytest

# Instalar pytest con cobertura (opcional)
pip install pytest pytest-cov

# Verificar instalación
pytest --version
```

## EJECUCIÓN PASO A PASO

1. Abre una terminal en la carpeta del proyecto
2. Navega hasta la carpeta que contiene la carpeta `tests/`
3. Ejecuta el comando deseado
4. Revisa los resultados en la terminal

**Ejemplo completo:**
```bash
cd /ruta/al/proyecto/POO-SmartHome
pytest tests/test_user.py -v
```

Este comando ejecutará todos los tests del archivo `test_user.py` con información detallada.
