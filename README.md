# Flow-MySQL

Este repositorio contiene el flow de NodeRed para obtener la informacion climatica por API y la relalizacion de una tabla en MySQL 


## Material necesario
Para poder realizar necesario es necesario tener instalado:
- [Node.js](https://github.com/nodesource/distributions/blob/master/README.md) Usar la versión LTS v16x e instalar los build tools.
- [Node-Red](https://nodered.org/docs/getting-started/local)
- Instalar dashboard, puedes consultar el como mediante la siguiente guía: [dashboard CodigoIoT](https://edu.codigoiot.com/mod/page/view.php?id=1080)
- [OpenWeatherMap](https://openweathermap.org). Servicio meteorológico gratuito. Se requiere cuenta, pero no se requiere ningun pago.

- MySQL, para poder instalrlo coloca los siguientes comandos en la terminal:
  >sudo apt update
  >sudo apt install mysql-server

-[Flow-5](https://github.com/ArathTzec/Flow-5)


## Notas

>No olvides primero abrir node red desde la terminal con node-red, de igual manera, abrir el **localhost:1880** en tu navegador de preferenecia
>El mensaje mqtt usado para probar este flow es `mosquitto_pub -h localhost -t ccodigoIoT/fow5/mqtt -m '{"ID":"Hugo Vargas","temp":18,"hum":78}'`

>Para arrancar MySQL Server se usa el siguiente comando sudo mysql

>Para mostrar las bases de datos creadas se usa el comandos show databases;

>Para ver las tablas de la base de datos seleccionada show tables;

>Para conocer los detalles de una tabla describe clima;

## Instrucciones

1. Arrancar NodeRed con el comando `node-red`
2. Importar el flow 5 del repositorio.
3. Coloca tu API Key personal en la API Call del nodo HTTP Request.
4. Actualiza la IP del broker público.
5. Hacer clic en el boton Deploy.

#### Configurar base de datos

Coloca los siguientes comandos: 

1. create database codigoIoT;
2. use codigoIoT;
3. create user '**Tu nombre de usuario**'@'localhost' identified by '**Tucontraseña**';
4. grant all privileges on *.* to '**Tu nombre de usuario**''@'localhost';
5. create table clima (id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY, fecha TIMESTAMP DEFAULT CURRENT_TIMESTAMP, nombre VARCHAR (248) NOT NULL, temperatura FLOAT (4,2) NOT NULL, humedad INT (3) NOT NULL);


>Estas instrucciones fueron proporcionadas por: [Hugo-Vargas](https://github.com/hugoescalpelo/flow5-NodeRed-ClimaAPI)

## Resultados
Una vez completados los pasos anteriores te dirigirá al Dashboard, que es la interfaz donde ver la temperatura y humedad dependiendo del mensaje que envies, trata de enviar el codigo que se encuentra en notas. Tambien recíbiras los datos de los demas compañeros
![](https://github.com/ArathTzec/Flow-5/blob/main/Dashboard-Flow5.png?raw=true)

Puedes ver los nodos en el siguiente link [Nodos-Flow5](https://github.com/ArathTzec/Flow-5/blob/main/Nodos%20node%20red%20flow%205-1.png)

## Evidencia 

Puedes encontrar el video explicativo en el siguiente enlace: [Youtube](https://www.youtube.com/watch?v=LmUY9topxeM)