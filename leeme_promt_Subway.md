# Proyecto: Subway (Primera Parte)

**Lenguaje:** Python
**Framework:** Django
**Editor:** VS Code

---

1.  **Crear carpeta del Proyecto:** `UIII_Subway_0689`.
2.  **Abrir VS Code:** Abrir VS Code sobre la carpeta `UIII_Subway_0689`.
3.  **Abrir Terminal:** Abrir la terminal integrada en VS Code.
4.  **Crear Entorno Virtual:** Crear la carpeta de entorno virtual `.venv` desde la terminal de VS Code.
5.  **Activar Entorno Virtual:** Procedimiento para activar el entorno virtual.
6.  **Activar Intérprete de Python:** Procedimiento para activar el intérprete de Python.
7.  **Instalar Django:** Procedimiento para instalar Django.
8.  **Crear Proyecto Backend:** Crear el proyecto `backend_Subway` sin duplicar la carpeta.
9.  **Ejecutar Servidor:** Procedimiento para ejecutar el servidor en el puerto `8039`.
10. **Copiar Link:** Copiar y pegar el link del servidor en el navegador.
11. **Crear Aplicación:** Procedimiento para crear la aplicación `app_Subway`.

---

### 12. Modelos (`models.py`)

```python
from django.db import models

# ==========================================
# MODELO: SUCURSALES
# ==========================================
class Sucursal(models.Model):
    nombre = models.CharField(max_length=50)
    telefono = models.CharField(max_length=15)
    horario_apertura = models.TimeField()
    horario_cierre = models.TimeField()
    direccion = models.CharField(max_length=100)
    def __str__(self):
        return self.nombre

# ==========================================
# MODELO: CLIENTES
# ==========================================
class Cliente(models.Model):
    nombre = models.CharField(max_length=100)
    direccion = models.CharField(max_length=200)
    telefono = models.CharField(max_length=15)
    correo = models.CharField(max_length=100)
    fecha_registro = models.DateField()
    sucursal = models.ForeignKey(Sucursal, on_delete=models.CASCADE, related_name="clientes")
    def __str__(self):
        return self.nombre

# ==========================================
# MODELO: EMPLEADOS
# ==========================================
class Empleado(models.Model):
    sucursal = models.ForeignKey(Sucursal, on_delete=models.CASCADE, related_name="empleados")
    telefono = models.CharField(max_length=15)
    salario = models.DecimalField(max_digits=10, decimal_places=2)
    fecha_contratacion = models.DateField()
    puesto = models.CharField(max_length=50)
    def __str__(self):
        return f"{self.puesto} - {self.sucursal.nombre}"
```
12.5. Realizar Migraciones: Procedimiento para realizar las migraciones (makemigrations y migrate).
13. Trabajar con el Modelo: Primero, trabajar con el MODELO: SUCURSALES.
14. Funciones en views.py: En views.py de app_Subway, crear las funciones con sus códigos correspondientes:
* inicio_subway
* agregar_sucursal
* actualizar_sucursal
* realizar_actualizacion_sucursal
* borrar_sucursal
15. Crear Carpeta templates: Crear la carpeta templates dentro de app_Subway.
16. Crear Archivos HTML Base: En la carpeta templates, crear los archivos HTML:
* base.html
* header.html
* navbar.html
* footer.html
* inicio.html
17. Integrar Bootstrap: En base.html, agregar Bootstrap para CSS y JS.
18. Configurar navbar.html: Incluir las siguientes opciones:
* "Sistema de Administración Subway"
* "Inicio"
* "Sucursales" (con submenú: "Agregar Sucursal", "Ver Sucursales", "Actualizar Sucursal", "Borrar Sucursal")
* "Clientes" (con submenú: "Agregar Cliente", "Ver Clientes", "Actualizar Cliente", "Borrar Cliente")
* "Empleados" (con submenú: "Agregar Empleado", "Ver Empleados", "Actualizar Empleado", "Borrar Empleado")
* Nota: Incluir iconos solo en las opciones principales (no en los submenús).
19. Configurar footer.html: Incluir derechos de autor, fecha del sistema y "Creado por Ing. Eliseo Nava, Cbtis 128". Mantenerlo fijo al final de la página.
20. Configurar inicio.html: Usar para colocar información del sistema más una imagen tomada de la red sobre Subway.
21. Crear Subcarpeta sucursal: Crear la subcarpeta sucursal dentro de app_Subway/templates.
22. Crear Archivos HTML para CRUD de Sucursal: Dentro de app_Subway/templates/sucursal, crear los archivos HTML con su código correspondiente:
* agregar_sucursal.html
* ver_sucursales.html (mostrar en tabla con botones "ver", "editar" y "borrar")
* actualizar_sucursal.html
* borrar_sucursal.html
23. No Usar forms.py: Abstenerse de utilizar forms.py.
24. Crear urls.py de la Aplicación: Procedimiento para crear el archivo urls.py en app_Subway con el código correspondiente para acceder a las funciones de views.py para operaciones CRUD en sucursales.
25. Agregar app_Subway a settings.py: Procedimiento para agregar app_Subway en settings.py de backend_Subway.
26. Configurar urls.py del Proyecto: Realizar las configuraciones correspondientes en urls.py de backend_Subway para enlazar con app_Subway.
27. Registrar Modelos en admin.py: Procedimiento para registrar los modelos en admin.py y volver a realizar las migraciones. Por lo pronto, solo trabajar con "Sucursal"; dejar pendientes los modelos "CLIENTES" y "EMPLEADOS".
28. Estilo de Diseño: Utilizar colores suaves, atractivos y modernos. El código de las páginas web debe ser sencillo.
28. Validación de Datos: No validar la entrada de datos.
29. Estructura Inicial: Al inicio, crear la estructura completa de carpetas y archivos.
30. Funcionalidad: El proyecto debe ser totalmente funcional.
31. Ejecución Final: Finalmente, ejecutar el servidor en el puerto 8036.
