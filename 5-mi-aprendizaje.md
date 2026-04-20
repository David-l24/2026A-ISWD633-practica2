# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Aprendí sobre el uso de variables de entorno y como agregarlas al crear un contenedor, redes privadas para realizar conexiones entre contenedores, y también aprendí como se realiza una conexión frontend a una backend en docker, con flujo de datos y como funcionan por separado junto a sus detalles, como el hecho de que la base de datos (back) no necesita saber que el front existe , en este caso wordpress, para funcionar.

## Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets)
Un Secreto es un objeto de datos (como una contraseña) que se almacena de forma cifrada y segura. A diferencia de las variables de entorno (que cualquiera con docker inspect puede ver), los secretos solo se entregan a los contenedores que realmente los necesitan.
### Almacenamiento seguro: 
El secreto se crea en el "Manager" de un cluster (usualmente con Docker Swarm). Se guarda cifrado.
### Transmisión segura: 
Cuando un contenedor que necesita el secreto se inicia, Docker lo descifra y lo "monta" como un archivo temporal en una carpeta especial dentro del contenedor: /run/secrets/.
### Memoria Volátil: 
El secreto nunca se escribe en el disco del contenedor; vive solo en la memoria RAM. Si el contenedor se detiene, el secreto desaparece de su vista.
