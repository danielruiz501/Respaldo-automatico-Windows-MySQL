# Respaldo-automatico-Windows-MySQL

1. Crear el script de respaldo

Crear un archivo llamado: en algun editor de texto llamado:

backup_mysql.bat


Con este contenido:

@echo off
set FECHA=%date:~-4%%date:~4,2%%date:~7,2%
set HORA=%time:~0,2%%time:~3,2%
set RUTA_RESPALDO=C:\backups_mysql

mkdir %RUTA_RESPALDO%

"C:\Program Files\MySQL\MySQL Server 8.0\bin\mysqldump.exe" -u root -pTU_PASSWORD ecommerce > %RUTA_RESPALDO%\backup_%FECHA%_%HORA%.sql


Reemplazar:

TU_PASSWORD


por contraseña real.

2. Configurar el Programador de tareas

Abrir Programador de tareas en Windows

Hacer clic en Crear tarea básica

Nombre: Respaldo MySQL

Eligir la frecuencia (diaria, semanal, etc.)

En Acción, seleccionar:

Programa/script: buscar el archivo backup_mysql.bat

3. Probar el respaldo

Hacer doble clic sobre el archivo .bat y verificar que se genere un .sql en:

C:\backups_mysql
