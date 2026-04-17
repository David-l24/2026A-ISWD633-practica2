# Redes

Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior.


![Imagen](redes.PNG)

* Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.

  * Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
  * Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
* Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
* None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create <nombre red> -d bridge
```

### Crear un contenedor vinculado a una red

```
docker run -d --name <nombre contenedor> --network <nombre red> <nombre imagen>
```

### Para saber a qué red está conectado un contenedor

```
docker inspect <nombre contenedor>
```

ó

```
docker network inspect <nombre red> 
```

### Vincular contenedor a una red

```
docker network connect <nombre red> <nombre contenedor>
```

### Para desvincular un contenedor de una red

```
docker network disconnect <nombre red> <nombre contenedor>
```

### Para listar las redes existentes

```
docker network ls
```

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)

# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS

# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS
## Contenedor vinculado a la red bridge creada por nosotros
<img width="1000" height="141" alt="image" src="https://github.com/user-attachments/assets/a86bcd94-4556-4dcb-8713-af2aae52fe4e" />

## Contenedor vinculado a la red bridge por defecto
<img width="984" height="79" alt="image" src="https://github.com/user-attachments/assets/cde61119-b885-4bef-b05f-a4f48d895430" />

## Contenedor vinculado a la red Host
<img width="941" height="64" alt="image" src="https://github.com/user-attachments/assets/63fbfc23-bd31-4bb2-942a-e690471635bb" />

## Contenedor vinculado a la red none
<img width="949" height="78" alt="image" src="https://github.com/user-attachments/assets/034373cf-b625-4cde-b598-615e0a531157" />

## Contenedor vinculado a la red bridge por defecto y a la creada
<img width="687" height="50" alt="image" src="https://github.com/user-attachments/assets/6aeae36f-ff99-4674-8747-8d2caf76b3b1" />

### Para eliminar las redes creadas

```
docker network rm <nombre de la red>
```

