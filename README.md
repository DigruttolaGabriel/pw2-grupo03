Logistica S.A.

Trabajo practico final para la materia Programacion Web 2 en UNLaM

Descripción general del sistema:

Logistica S.A. utiliza un sistema informático para controlar su flota de vehículos.

La empresa cuenta con una importante flota propia de vehículos y realiza viajes a todo el país.
El sistema permite el acceso desde cualquier conexión a internet, puesto que se utilizará para
chequear en todo momento la posición y recorrido de los vehículos durante los viajes.

El sistema permite cinco niveles de acceso (roles):
- Administrador: encargado de administrar el sistema, trabajar con los reportes de nivel gerencial y realizar la carga de roles y usuarios.
Funcionalidades disponibles para el rol: Usuarios, Reportes (Generar Proforma y Mantenimiento de Vehículos), Clientes, Flota de Vehiculos, Facturas, Consultar posición de vehículo, Mantenimiendo de Vehiculos, Viajes.
- Supervisor: Realiza las tareas de carga y consulta de los datos en las oficinas centrales.
Funcionalidades disponibles para el rol: Clientes, Flota de Vehiculos, Facturas, Consultar posición de vehículo, Viajes.
- Encargado del taller: Actualiza los datos de mantenimiento.
Funcionalidades disponibles para el rol: Consultar Posicion de vehiculo, Mantenimiento de Vehículos.
- Chofer: Utiliza el sistema para actualizar los datos durante el viaje.
Funcionalidades disponibles para el rol: Viajes.
- Mecanico: Realiza el mantenimiento de los vehiculos, este no utiliza la aplicación.


Descripción de funcionalidades:

- Seguridad del sistema (autenticación y autorización (según rol por ejemplo) en toda la aplicación).
- ABM de usuarios, Roles, Log-in, manejo de claves y permisos. Todos los usuarios se registran como usuarios
llanos y el administrador les otorga roles una vez registrados.
- Administración de la flota de vehículos. ABM, estado, reportes, posición actual, etc.
- Administración del plantel de empleados.
- Administración de Viajes. ABM, vehículo, origen, destino, chofer asignado, cliente, tipo de carga,
fechas, tiempo estimado de viaje, tiempo real, desviación, kilómetros recorridos previstos,
kilómetros recorridos reales, combustible consumido (previsto y real), etc.
- Mantenimiento de los vehículos. ABM, services, km de la unidad, costo, service
interno/externo, mecánico interviniente, repuestos cambiados, etc.
- Seguimiento de los vehículos en viaje. En cualquier momento el supervisor, el administrador y/o
el encargado de taller pueden consultar la posición actual del vehículo en un mapa.
- Facturación de los viajes a los clientes en base a la proforma generada.

La aplicación permite a los choferes mediante los celulares que se les
entregan, y a partir de un código leído de un QR, enviar un reporte diario de posición a partir del GPS del
celular. Se genera un codigo QR único para cada viaje, de
manera de poder realizar el seguimiento correspondiente. A través de la misma aplicación los choferes
informan cargas de combustible, desvios, posición actual y gastos.

Para cada viaje se asigna un chofer, una unidad de transporte y un remolque.


Detalles técnicos:

• Se utiliza una base de datos MySql para almacenar los datos.
• El sistema está implementado con el lenguaje de programación PHP desde el lado del Servidor.
• La arquitectura de la aplicación está basada en un modelo MVC.
• La interfaz está implementada en el Framework W3.CSS.
• El manejo de posicionamiento y mapas se realiza mediante HTML Geolocation API.


Login de varios usuarios ejemplo:
** Por motivos de seguridad no se proporciona un login de administrador. **

EMAIL - CONTRASEÑA - ROL:

- marialopez@gmail.com - marialopez - Supervisora
- franciscovegas@gmail.com - franciscovegas - Encargado de Taller
- gastonperez@gmail.com - gastonperez - Chofer
- mariogimenez@gmail.com - mariogimenez - Chofer
- rodrigoelizald@gmail.com - rodrigoelizald - Chofer
- juanperez@gmail.com - juanperez - Chofer
- mariorodriguez@gmail.com - mariorodriguez - Chofer


Carga de datos de un viaje:

Los choferes informan datos del viaje a partir de un codigo QR generado en la proforma, que llevan a una URL dinamica https://fleshly-trials.000webhostapp.com/travel/loadData?id=[ID DE VIAJE]. Esta proforma es impresa y los choferes deberan llevarla con ellos/as para poder acceder al QR y/o ver datos del viaje.

Ejemplo: Loguearse con el usuario juanperez@gmail.com e ir a Viajes. La proforma del viaje con ID 5 contiene un QR que dirige a https://fleshly-trials.000webhostapp.com/travel/loadData?id=5, allí se podran informar nuevos datos del viaje.
