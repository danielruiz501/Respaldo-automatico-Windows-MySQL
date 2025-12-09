# Backup-automatico-Windows-MySQL


1. Crear el script de backups

Crear un archivo en algun editor de texto llamado:

backup_ecommerce.bat

Con este contenido:

cd C:\Program Files\MySQL\MySQL Server 8.0\bin

mysqldump -uroot -p ecommerce > "C:\MyBackups\ecommercebackup.sql"

Para todas las bases de datos:
mysqldump -uroot -p -all-databases > "C:\MyBackups\alldb.sql"

Y para una sola tabla: 
mysqldump -uroot -p ecommerce custommers > "C:\MyBackups\customersbackup.sql"


2. Configurar el Programador de tareas
   
Abrir Programador de tareas en Windows, hacer clic en Crear tarea básica

Nombre: Respaldo MySQL

Eligir la frecuencia (diaria, semanal, etc.)

En Acción, seleccionar:

Programa/script: buscar el archivo backup_ecommerce.bat


3. Probar el respaldo

Hacer doble clic sobre el archivo .bat y verificar que se genere un .sql en:

C:\Mybackups


4. Esperar a que se active el respaldo automàtico

Esperar a la configuraciòn establecida para que el respaldo se genere de manera automàtica.
