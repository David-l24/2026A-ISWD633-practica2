## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR
C:\Users\wwwal>docker network create net-wp

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR
>docker run -d --name srv-mysql8 --network net-wp -e MYSQL_ROOT_PASSWORD=admin mysql:8
<img width="1221" height="314" alt="image" src="https://github.com/user-attachments/assets/404dba9d-1fb7-49c6-8b34-e44b2737ce42" />

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
docker run -d --name cont-wordpress --network net-wp -p 8080:80 -e WORDPRESS_DB_HOST=srv-mysql8 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=admin -e WORDPRESS_DB_NAME=wordpress wordpress
<img width="1249" height="310" alt="image" src="https://github.com/user-attachments/assets/7928f7f0-c3c2-4454-aba1-8ccda4293b47" />

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **8080**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
<img width="1235" height="969" alt="image" src="https://github.com/user-attachments/assets/d58596b4-25e3-4bbd-9d89-e7da3ad23751" />

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
<img width="1895" height="777" alt="image" src="https://github.com/user-attachments/assets/32c59151-1965-47b5-b87c-7e60500938d5" />
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="1746" height="833" alt="image" src="https://github.com/user-attachments/assets/3b5961d9-076d-456c-a462-abd63f5b027a" />

### Eliminar el contenedor wordpress
# COMPLETAR
<img width="548" height="180" alt="image" src="https://github.com/user-attachments/assets/0ec13436-ac5e-488e-b1a4-8cc7e15a1bf6" />

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR
que se puede ingresar directamente a la página de wordpress que teníamos al momento de eliminarla anteriormente, junto al tema seleccionado y a la publicación creada, esto gracias a que los cambios se guardaron en la base de datos de mysql que tenemos creada
