# AWSRekognitionTopicos
Proyecto para la materia de Topicos Especiales en Telematica con las herramientas de AWS\

 El proyecto AWS Rekognition es una pagina web en la cual cada persona podrá subir sus fotos desde cualquier plataforma y acceder a estas en cualquier momento. Cada foto sera analizada por los algoritmos de AWS Rekognition para identificar detalles tales como quienes están en la foto, si son hombres o mujeres, si están felices o tristes, su vestimenta, el lugar en el que están entre otros. 

 El proyecto se desarrollo con las siguientes tecnologías:

 ###  AWS Identity and Access Management (IAM)
> es un servicio web que le ayuda a acceder de forma segura a los recursos de AWS. Normalmente utilizamos las credenciales de los usuarios de IAM o las funciones de IAM para autenticar con AWS al realizar llamadas a la API. Controlamos los permisos para las acciones de API que esos usuarios o roles pueden realizar con las políticas de IAM.

## AWS Cloud9
> es un entorno de desarrollo integrado basado en la nube (IDE) que le permite escribir, ejecutar y depurar su código con solo un navegador. Incluye un editor de código, depurador y terminal. Puede ejecutar este entorno de desarrollo en una instancia administrada de Amazon EC2 que duerme automáticamente cuando no la está utilizando.

 ## Amazon Simple Storage Service (S3)
> es el almacenamiento de objetos creado para almacenar y recuperar cualquier cantidad de datos desde cualquier lugar: sitios web y aplicaciones móviles, aplicaciones corporativas y datos de sensores o dispositivos IoT. Puede almacenar archivos como Objetos dentro de S3 Buckets.

## Amazon Rekognition 
> es un servicio que aplica el aprendizaje profundo para analizar el contenido de imágenes y videos. Es compatible con la funcionalidad de detección de escena, detección de rostros e incluso reconocimiento de celebridades. En esta clase, estamos utilizando la funcionalidad Detectar etiquetas que toma una imagen como entrada y devuelve etiquetas con valores de confianza como {Nombre: faro, Confianza: 98.4629}

## Amazon Relational Database service
> le permite ejecutar una instancia de db administrada con uno de los 6 motores de base de datos relacionales, como MySQL, que estamos utilizando en esta clase. AWS aplicará parches al software en la instancia en su nombre y programará copias de seguridad diarias. Puede ejecutar su base de datos de forma privada, dentro de su VPC y también puede configurarla para ejecutarse en una implementación multi-AZ.

## Amazon Elastic Load Balancer
> proporciona varios tipos de equilibrador de carga como un servicio administrado. En este curso, estamos utilizando Application Load Balancer para que podamos aislar a los usuarios de nuestros servidores de aplicaciones. Esto nos permite operar servidores redundantes para mejorar el tiempo de actividad de nuestra aplicación y en el futuro, ejecutar múltiples servidores para que podamos escalar nuestra aplicación para manejar a más usuarios.

## Amazon Cognito User Pools
> Cree y mantenga un directorio de usuarios, agregue registro e inicie sesión en su aplicación móvil o aplicación web utilizando grupos de usuarios. Los grupos de usuarios escalan a cientos de millones de usuarios y están diseñados para brindarle opciones simples, seguras y de bajo costo para usted como desarrollado

## AWS Certificate Manager (ACM) 
> puede ayudarlo a implementar sus certificados SSL / TLS en su infraestructura de AWS, como Application Load Balancer. Si no tiene un certificado, ACM también puede remitirle un certificado.

## AWS X-Ray 
> ayuda a los des arrolladores a analizar aplicaciones distribuidas. Con X-Ray, puede comprender cómo se desempeñan su aplicación y sus servicios subyacentes para identificar y solucionar los problemas y errores de rendimiento. X-Ray proporciona una vista de extremo a extremo de las solicitudes mientras viajan a través de su aplicación, y muestra un mapa de los componentes subyacentes de su aplicación.
.
## AWS Lambda
> le permite ejecutar código sin aprovisionar o administrar servidores. AWS Lambda ejecuta su código solo cuando es necesario y escala automáticamente, desde unas pocas solicitudes por día hasta miles por segundo. Solo pagas por el tiempo de cómputo que consumes; no hay cargo cuando tu código no se está ejecutando.

# Instalacion y ejecucion del proyecto

Para ejecutar el proyecto se debe crear un nuevo proyecto en AWS Cloud9. Esto se hace dando click sobre Create environment:

> ![alt text](https://i.imgur.com/TfFZI3Y.png)

Ahora hay que agregar el proyecto a Cloud9 dando click sobre File y luego sobre Upload Local Files... y arrastre la capeta AWSRekognitionTopicos a el recuadro que aparece a continuacion:

> ![alt text](https://i.imgur.com/7uzLo0h.png)

Ahora vaya a la parte inferior de la pantalla y agregue una nueva ejecucion de arranque: 

> ![alt text](https://i.imgur.com/wZAX245.jpg)

En la nueva configuracion de ejecuccion creada en el paso anterior, de click sobre ENV e ingrese las siguentes variables:

> ##### PHOTOS_BUCKET: bucketphotostopicos

> ##### FLASK_SECRET: topicos

> ##### DATABASE_HOST: edx-photos-db.csibdpprrn9n.us-west-2.rds.amazonaws.com

> ##### DATABASE_USER: web_user

> ##### DATABASE_PASSWORD: topicostelematica

> ##### DATABASE_DB_NAME: Photos

> ##### COGNITO_POOL_ID: us-west-2_LpJ4qZpEH

> ##### COGNITO_CLIENT_ID: 44rjqt5gpt1o643hk13v0gm29t

> ##### COGNITO_CLIENT_SECRET: 155dc910huh95us53m85ol5is5boittitf6r4es0g2tq8hg9mkt

> ##### COGNITO_DOMAIN: topicosproject.auth.us-west-2.amazoncognito.com

> ##### BASE_URL: http://localhost:5000

> ![alt text](https://i.imgur.com/t7PPafC.png)

Ejecute el proyecto y en la parte superior de la pantalla de click sobre Share y copie la ip que hay dentro del campo Application.

Por ultimo cree un puente entre la ip y localhost con el siguiente comando dentro de una consola: 

> ssh -i CREDENCIALES(Preguntar por estas).pem ec2-user@ACA_VA_LA_IP_ANTERIOR -L 5000:localhost:5000

Ahora puede ingresar a http://localhost:5000/
