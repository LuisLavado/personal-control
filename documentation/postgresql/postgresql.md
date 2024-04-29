* Respaldar base de datos desde la consola de Windows:

"C:\Program Files\PostgreSQL\16\bin\pg_dump.exe" --host localhost --port 5432 --username postgres --password --role postgres --format=c --verbose --file "D:\control_personal.sql" control-personal

Te pedirá la una contraseña, pon la contraseña de PostgreSQL

* Restaurar base de datos desde la consola de Windows:

1) Abrir la línea de comandos: Abre la línea de comandos de Windows. Puedes hacerlo buscando "cmd" en el menú de inicio y ejecutándolo.
2) Navegar a la ubicación de la herramienta pg_restore: Si tienes PostgreSQL instalado, la ubicación de pg_restore normalmente estará en el directorio bin dentro del directorio de instalación de PostgreSQL. Si PostgreSQL está instalado en la ubicación predeterminada, puedes navegar allí usando el comando cd:

cd C:\Program Files\PostgreSQL\<version>\bin

3) Ejecutar el comando pg_restore: Una vez en el directorio bin, puedes ejecutar el comando pg_restore para restaurar la base de datos. El comando generalmente tiene esta forma:
pg_restore -U <nombre_de_usuario> -d <nombre_de_base_de_datos> <archivo_de_respaldo.dump>
psql -U <nombre_de_usuario> -d <nombre_de_base_de_datos> -f <archivo_de_script_sql>


Donde:
<nombre_de_usuario> es el nombre de usuario de PostgreSQL que tiene permisos para restaurar la base de datos.
<nombre_de_base_de_datos> es el nombre de la base de datos a la que se restaurarán los datos.
<archivo_de_respaldo> es la ruta del archivo de respaldo que quieres restaurar.
Por ejemplo:
pg_restore -U postgres -d mydatabase C:\backup\backup_file.dump
psql -U postgres -d mydatabase -f C:\backup\backup_file.sql

psql -U postgres -d test-backup -f D:\control-personal-backup-2024.sql

pg_restore -U postgres -d test-backup D:\control-personal-backup-2024.sql


