# Variables de Entorno
### ¿Qué son las variables de entorno?
Son variables que se asignan localmente en el sistema, son configuraciones que en algunos casos son necesarias definir para llevar acciones específicas.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR
<img width="1119" height="142" alt="image" src="https://github.com/user-attachments/assets/6a68654e-ba76-4836-853c-ae9f2b748284" />

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR
<img width="1019" height="521" alt="image" src="https://github.com/user-attachments/assets/142050c7-902c-4fb3-8a61-c7527ecb55b0" />


### ¿El contenedor se está ejecutando?
# COMPLETAR
No, no se está ejecutando

### Identificar el problema
# COMPLETAR
Hizo falta asignar una variable de entorno obligatoria para un contenedor mysql, que sin el el contenedor sólo se encenderá y se apagará inmediatamente. Ya que mysql exige que se le de una contraseña de administrador a utilizar, y también fallé al ubicar los comandos, los ubiqué después del nombre y la imagen, pero en realidad debían ir antes.
.
### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

<img width="1706" height="195" alt="image" src="https://github.com/user-attachments/assets/6ec6760f-c72c-4e5f-946f-50604d90adf7" />

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
<img width="995" height="628" alt="image" src="https://github.com/user-attachments/assets/c458ec34-35fa-4f0e-a10d-7ed537fa130f" />
