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

**Caso de uso:** 

**Actor Primario:** cámara (primario)

**Caminos Básico:**

1. La cámara envía los datos al sistema  
2. El sistema registra y luego evalúa los datos sobre la velocidad  
   

**Camino Alternativo:**  
2.a El sistema detecta que el vehículo conduce a una velocidad menor a 70 km/h.  
2.b El sistema no envía ningún dato. fin del caso de uso

2.a El sistema envía los datos a una API que se encargará de guardarlos en una base de datos.  
2.b El sistema envía un correo con los datos que envió la cámara a la cuenta "alertas@ciudad". fin del caso de uso

2.a El sistema envía los datos a una API que se encargará de guardarlos en una base de datos  
2.b El sistema envía un correo con los datos que envió la cámara a la cuenta "alertas@ciudad".  
2.c El sistema envía, 3 veces, los datos recibidos por la cámara a una impresora para que sean impresos. fin del caso de uso

**Escenario de éxito:** El sistema recibir, evalúa y envía todos los datos a una API.

**Escenario de fracaso:** \-  
