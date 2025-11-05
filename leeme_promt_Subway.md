Primera parte
Proyecto: Subway.
lenguaje: Python.
Framework: Django.
Editor: VS code.
1 Procedimiento para crear carpeta del Proyecto: UIII_Subway_0777
2 procedimiento para abrir vs code sobre la carpeta
UIII_Subway_0777
3 procedimiento para abrir terminal en vs code
4 Procedimiento para crear carpeta entorno virtual “.venv” desde
terminal de vs code
5 Procedimiento para activar el entorno virtual.
6 procedimiento para activar intérprete de python.
7 Procedimiento para instalar Django
8 procedimiento para crear proyecto backend_Subway sin duplicar
carpeta.
9 procedimiento para ejecutar servidor en el puerto 8036
10 procedimiento para copiar y pegar el link en el navegador.
11 procedimiento para crear aplicacion app_Subway
12 Aqui el modelo models.py
=-=-=-=-=-
from django.db import models
==========================================
MODELO: SUCURSALES
==========================================
class Sucursal(models.Model):
nombre = models.CharField(max_length=50)
telefono = models.CharField(max_length=15)
horario_apertura = models.TimeField()
horario_cierre = models.TimeField()
direccion = models.CharField(max_length=100)
# id_empleado no es un campo directo en el modelo de Django para una relación 1 a muchos desde Empleado
# se gestionaría a través de la relación inversa desde Empleado.
def str(self):
return self.nombre
==========================================
MODELO: CLIENTES
==========================================
class Cliente(models.Model):
nombre = models.CharField(max_length=100)
direccion = models.CharField(max_length=200)
telefono = models.CharField(max_length=15)
correo = models.CharField(max_length=100)
fecha_registro = models.DateField()
sucursal = models.ForeignKey(Sucursal, on_delete=models.CASCADE, related_name="clientes")
def str(self):
return self.nombre
==========================================
MODELO: EMPLEADOS
==========================================
class Empleado(models.Model):
sucursal = models.ForeignKey(Sucursal, on_delete=models.CASCADE, related_name="empleados")
telefono = models.CharField(max_length=15)
salario = models.DecimalField(max_digits=10, decimal_places=2)
fecha_contratacion = models.DateField()
puesto = models.CharField(max_length=50) # Cambiado a CharField para el puesto
def str(self):
return f"{self.puesto} - {self.sucursal.nombre}"
=-=-=-=-=-
12.5 Procedimiento para realizar las migraciones(makemigrations y
migrate.
13 primero trabajamos con el MODELO: SUCURSALES
14 En view de app_Subway crear las funciones con sus códigos
correspondientes (inicio_subway, agregar_sucursal,
actualizar_sucursal, realizar_actualizacion_sucursal,
borrar_sucursal)
15 Crear la carpeta “templates” dentro de “app_Subway”.
16 En la carpeta templates crear los archivos html (base.html,
header.html, navbar.html, footer.html, inicio.html).
17 En el archivo base.html agregar bootstrap para css y js.
18 En el archivo navbar.html incluir las opciones ( “Sistema de
Administración Subway”, “Inicio”, “Sucursales”,en submenu de
sucursales(Agregar Sucursal,ver Sucursal, actualizar Sucursal,
borrar Sucursal), “Clientes” en submenu de Clientes(Agregar Cliente,ver
Cliente, actualizar Cliente, borrar Cliente)
“Empleados” en submenu de Empleados(Agregar Empleado,ver Empleado,
actualizar Empleado, borrar Empleado), incluir iconos a las opciones
principales, no en los submenu.
19 En el archivo footer.html incluir derechos de autor,fecha del
sistema y “Creado por Ing. Eliseo Nava, Cbtis 128” y mantenerla fija
al final de la página.
20 En el archivo inicio.html se usa para colocar información del
sistema más una imagen tomada desde la red sobre Subway.
21 Crear la subcarpeta carpeta sucursal dentro de
app_Subway\templates.
22 crear los archivos html con su codigo correspondientes de
(agregar_sucursal.html, ver_sucursales.html mostrar en tabla con
los botones ver, editar y borrar, actualizar_sucursal.html,
borrar_sucursal.html)
dentro de app_Subway\templates\sucursal.
23 No utilizar forms.py.
24 procedimiento para crear el archivo urls.py en app_Subway con
el código correspondiente para acceder a las funciones de views.py
para operaciones de crud en sucursales.
25 procedimiento para agregar app_Subway en settings.py de
backend_Subway
26 realizar las configuraciones correspondiente a urls.py de
backend_Subway para enlazar con app_Subway
27 procedimiento para registrar los modelos en admin.py y volver a
realizar las migraciones.
27 por lo pronto solo trabajar con “Sucursal” dejar pendiente #
MODELO: CLIENTES y # MODELO: EMPLEADOS
28 Utilizar colores suaves, atractivos y modernos, el código de las
páginas web sencillas.
28 No validar entrada de datos.
29 Al inicio crear la estructura completa de carpetas y archivos.
30 proyecto totalmente funcional.
31 finalmente ejecutar servidor en el puerto puerto 8036.
