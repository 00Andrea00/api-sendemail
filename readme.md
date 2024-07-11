## API
Servicio web para enviar correos electrónicos a una dirección de email concreta para soporte, con nombre del emisor y un mensaje.

### Instalación
No requiere de instalación, los pasos a seguir para su uso son:  
- Acceder al repositorio de GitHub https://github.com/00Andrea00/api-sendemail.git
- Descargar los archivos en una carpeta del servidor local

### Uso
- Abrir la carpeta con el servidor local
- Introducir los datos solicitados (nombre-name, email, mensaje-message) para el envío del email
- Pulsar Send Request para enviarlo
- Habrá tres posibles respuestas:  
  1. 200 OK - Correo enviado exitosamente
  2. 404 NOT FOUND - Fallo en el webservice
  3. 500 ERROR - Fallo al enviar el correo

### Ejemplo
```
# Envío exitoso del correo, todos los datos se han introducido correctamente

POST http://localhost/api/v1/endpoint-webservice/

{
  "name": "Andrea",
  "email": "andreacuencardzo@gmail.com",
  "message": "Hola mundo"
}

# Error en el envío del correo debido a que el campo name esta en blanco

###Dato faltante###
POST http://localhost/api/v1/endpoint-webservice/

{
  "name": "",
  "email": "andreacuencardzo@gmail.com",
  "message": "Hola mundo"
}

# Error en el envío del correo por un fallo en la escritura del campo email

###Email erróneo###
POST http://localhost/api/v1/endpoint-webservice/

{
  "name": "Andrea",
  "email": "andreacuencardzo@.com",
  "message": "Hola mundo"
}

# Error en el envío del correo por estar todos los campos en blanco

###Sin datos###
POST http://localhost/api/v1/endpoint-webservice/

{
  "name": "",
  "email": "",
  "message": ""
}

```