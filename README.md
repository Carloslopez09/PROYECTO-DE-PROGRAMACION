# PROYECTO-DE-PROGRAMACION

Autor: Grupo Numero 1
Curso: Programación II
Institución: Universidad Mariano Galves de Guatemala

Sistema de gestión de escritorio para un gimnasio, desarrollado en Java (Swing) con base de datos MySQL. Permite administrar clientes, membresías y pagos, la asistencia de los coaches, las máquinas y su mantenimiento, las rutinas de entrenamiento y los reportes, con acceso diferenciado por rol.

-Contenido-

Roles y permisos

Tecnologías

Requisitos

Instalación y ejecución

Usuario de prueba

Estructura del proyecto

Base de datos

Diagramas

Capturas de pantalla

Validaciones y seguridad

Autor


-Características-


Inicio:	Resumen con clientes activos, membresías por vencer, ingresos del mes y máquinas en mantenimiento, más la tabla de próximos vencimientos.

Clientes:	Registrar, editar y buscar clientes, darlos de baja (baja lógica) y registrar sus visitas.

Membresías y pagos:	Asignar una membresía y cobrarla en una sola transacción, cancelarla y consultar el historial de pagos.

Coaches:	Registrar coaches con su foto y crear su usuario de acceso.

Asistencia de coaches:	Marcar entrada y salida, filtrar por coach y fechas, y calcular las horas trabajadas.

Rutinas:	Subir archivos de Excel (xlsx, xls, xlsm, csv), listarlos y abrirlos con Excel.

Máquinas:	Inventario con categoría, marca, serie, fecha de adquisición, estado y foto.

Mantenimiento:	Registrar fallas y mantenimientos preventivos o correctivos, con seguimiento. El estado de la máquina se actualiza solo.

Reportes:	Seis reportes (clientes por vencer, clientes sin membresía vigente, horas por coach, máquinas en mantenimiento, ingresos por mes y resumen de clientes), con exportación a CSV.

Usuarios:	Crear administradores y recepcionistas, activarlos o desactivarlos y cambiar contraseñas.


-Tecnologías-
Lenguaje: Java (JDK 8 o superior)

Interfaz gráfica: Java Swing, diseñada con el editor visual de NetBeans

Base de datos: MySQL 

Acceso a datos: JDBC con MySQL Connector/J

IDE: Apache NetBeans


-Requisitos-
JDK 8 o superior instalado.

Apache NetBeans.

MySQL Connector/J (mysql-connector-j-8.x.jar), descargable en https://dev.mysql.com/downloads/connector/j/ (elige "Platform Independent").


-Base de datos-

Roles del sistema (administrador, coach, recepcionista)

Usuarios con su contraseña en hash y su rol

Datos de los clientes del gimnasio

tipos_membresia	Mensual, trimestral, anual y por sesiones, con su precio

Membresías asignadas, con fechas de inicio y vencimiento

Pagos de cada membresía y quién los registró

Visitas de los clientes

Datos del coach, su foto y su usuario de acceso

asistencia_coach	Hora de entrada y salida de cada coach

Inventario de máquinas, con foto

Fallas y mantenimientos de cada máquina

Archivos de Excel de rutinas


-Validaciones y seguridad-

Las contraseñas se guardan como hash SHA-256, nunca en texto plano.

Todas las consultas usan PreparedStatement con parámetros, lo que evita la inyección SQL.

El acceso a cada pantalla depende del rol del usuario.

La membresía y su pago se guardan en una transacción (commit / rollback).

Validaciones de campos obligatorios, formato de fecha y de números, usuarios duplicados, tamaño de archivos y reglas del negocio (por ejemplo, no marcar dos entradas seguidas).

Los errores se manejan con try-catch y se muestran al usuario en mensajes claros, sin cerrar el programa.

Los registros no se borran: se dan de baja cambiando su estado, para conservar el historial.
