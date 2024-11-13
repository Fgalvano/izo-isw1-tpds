# Trabajo Final de Ingeniería en Software

* Identifique los requerimientos.  
* Confeccione el diccionario de datos.  
* Identifique las reglas de negocio.  
* Realice el caso de uso.  
* Construya el diagrama entidad-relación y el diagrama de clases.  
* Realice el diagrama de secuencia.

Una cámara de video control vial, mide la velocidad con la que los autos pasan por una calle. En la ciudad, se cuentan con *“n”* cantidad de cámaras. Cada cámara detecta automáticamente al vehículo cuando pasa y envía a nuestro sistema los siguientes datos: fecha y hora, id de la cámara, patente y velocidad. El paso de cada vehículo deberá registrarse en el sistema. Cada cámara tiene un id, una descripción, coordenadas x e y de su ubicación, dirección IP y modelo de la cámara. El sistema debe funcionar 24/7.

Cuando el sistema recibe los datos de un vehículo que pasó, el sistema realiza distintas acciones según la velocidad:

* si la velocidad es mayor a 70 km/h:  
  * el sistema envía los datos a una API que se encargará de guardarlos en una base de datos  
  * el sistema envía un correo con los datos que envió la cámara a la cuenta "avisos@ciudad"  
* si la velocidad es mayor a 100 km/h:  
  * el sistema envía los datos a una API que se encargará de guardarlos en una base de datos  
  * el sistema envía un correo con los datos que envió la cámara a la cuenta "alertas@ciudad"  
  * el sistema envía, 3 veces, los datos recibidos por la cámara a una impresora para que sean impresos

**El diccionario de datos:**

Camara \= idCam \+ descripciónCam \+ ipCam \+ modeloCam   
fecha \= fecha \+ hora  
Vehiculo \= velocidad \+ patente  
Ubicacion \= coordenadasX \+ coordenadasY

| Nombre | Descripción | Tipo | Longitud | Dominio |
| ----- | ----- | ----- | ----- | ----- |
| velocidad | indicador de la velocidad | string | 7 | continuo |
| patente | patente del auto | string | 7 | continuo |
| fecha | indicador del dia | date | \- | continuo |
| hora | indicador de la hora | time | \- | continuo |
| idCam | id de la camara | entero | 20 | continuo |
| descripcionCam | descripción de la camara | string | 900 | continuo |
| coordenadasX | coordenada x de la camara | float | 20 | continuo |
| coordenadasY | coordenada y de la camara | float | 20 | continuo |
| ipCam | ip de la camara | string | 16 | continuo |
| modeloCam | modelo de la camara | string | 1000 |  |

