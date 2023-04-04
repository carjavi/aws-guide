
<p align="center"><img src="https://raw.githubusercontent.com/carjavi/aws-guide/master/img/AWS.png" height="200" alt=" " /></p>
<br>
<h1 align="center">Amazon Web Service Guide</h1> 
<h4 align="right">Dec 17</h4>
<img src="https://img.shields.io/badge/OS-Linux%20GNU-yellowgreen">
<img src="https://img.shields.io/badge/OS-Windows%2011-blue">
<img src="https://img.shields.io/badge/OS%20-Raspbian%20GNU%2FLinux%2011%20(bulleye)-yellowgreen">

<br>

# AWS IoT

Link AWS-IoT: https://docs.aws.amazon.com/es_es/iot/latest/developerguide/iot-dg.pdf#what-is-aws-iot

SDK: https://aws.amazon.com/es/iot/sdk/

Soporte AWS IoT: aws-iot-button@amazon.com

<br>

# Getting Your Credentials
When you create an AWS account, your account is provided with root credentials. Those credentials consist of two access keys:

credenciales de AWS account root user
* Access key ID
* Secret access key

Se utilizan diferentes tipos de credenciales de seguridad, en función de cómo se interaccione con AWS. Por ejemplo, puede utilizar un nombre de usuario y una contraseña para iniciar sesión en la Consola de administración de AWS.

# Los certificados de CA raíz:?
## root CA for AWS IoT

* La comunicación entre su dispositivo y AWS IoT se protege mediante certificados X.509. Los certi ficados deben activarse para poder usarlos.
* Los puertos reservados son el 1883 / 8883
* Amazon limita a los clientes a un Botón por cada marca de Dash Button
* Todo el tráfico desde y hacia AWS es encriptado sobre TLS (transport layer security)
* En las Políticas de AWS IoT  el ARN restringe qué clientes (dispositivos) pueden conectarse. sample: arn:aws:iot:your-region:your-aws-account:client/<my-client-id>. Si colocamos * se conectan todos.


1.	Creación y activación de un certificado de dispositivo (La comunicación entre su dispositivo y AWS IoT se protege mediante certificados X.509)

# Politicas AWS
Creación de una política de AWS IoT (Las políticas de AWS IoT se utilizan para autorizar a su dispositivo a ejecutar operaciones de AWS IoT, como suscribirse a temas MQTT o publicar en ellos. Para permitir a su dispositivo llevar a cabo operaciones de AWS IoT, debe crear una política de AWS IoT y asociarla al certificado de su dispositivo.) Sample=
*	iot:*
*	resuorce ARN: *
*	iot:Connect // representa el permiso para conectarse con el agente de mensajes de AWS IoT.
*	iot:Subscribe // representa el permiso para suscribirse a un tema MQTT o un filtro de temas.
*	iot:GetThingShadow //representa el permiso para obtener una sombra de objeto.

Una política de AWS IoT es un documento JSON que contiene una o varias declaraciones de política. Cada declaración contiene un Effect, una Action y un Resource. El Effect especifica si se permitirá o se denegará la acción. La Action especifica la acción que la política permite o deniega. El Resource especifica los recursos en los que se permite o se deniega la acción


# SDK
Un kit de desarrollo de software es generalmente un conjunto de herramientas de desarrollo de software que le permite al programador o desarrollador de software crear una aplicación informática para un sistema concreto, por ejemplo ciertos paquetes de software, frameworks, plataformas de hardware, computadoras, videoconsolas, sistemas operativos, etcétera.

# SDK para AWS IoT
El SDK para dispositivos con AWS IoT le ayuda a establecer una conexión rápida y sencilla de su dispositivo hardware con AWS IoT. Le proporciona características mejoradas que permiten que su dispositivo hardware funcione a la perfección y de forma segura con la puerta de enlace para dispositivos y con la alternativa de dispositivo proporcionados por AWS IoT.

# MQTT Connection / Cliente Test en AWS IoT
Es un ligero protocolo de comunicación cliente servidor de publicación/ suscripción. MQTT   is  a   machine-to-machine  (M2M) / "Internet  of  Things" connectivity  protocol.
MQTT son las siglas de Message Queue Telemetry Transport y tras ellas se encuentra un protocolo ideado por IBM y liberado para que cualquiera podamos usarlo enfocado a la conectividad Machine-to-Machine (M2M). Está enfocado al envío de datos en aplicaciones donde se requiere muy poco ancho de banda. Además, sus características le permiten presumir de tener un consumo realmente bajo así como precisar de muy pocos recursos para su funcionamiento.
Este tipo de arquitecturas, lleva asociada otra interesante característica: la comunicación puede ser de uno a uno o de uno a muchos.

ARN (Amazon Resource Name)

Thing ARN (A thing Amazon Resource Name uniquely identifies this thing.)

TLS (transport layer security) encriptación.

QoS calidad de servicio

# RULE AWS
Son básicamente los filtros de temas. Los mensajes publicados en temas que coincide con el filtro de tema activan la regla.

# AWS CLI
Interfaz de línea de comandos de AWS. La interfaz de línea de comandos (CLI) es una herramienta unificada para administrar los productos de AWS. Solo tendrá que descargar y configurar una única herramienta para poder controlar varios servicios de AWS desde la línea de comando y automatizarlos mediante secuencias de comandos. Ejemplos.
```
$ aws sns publish --topic-arn arn:aws:sns:us-east-1:546419318123:OperationsError --message "Script Failure"
$ aws sqs receive-message --queue-url https://queue.amazonaws.com/546419318123/Test
```

# IAM
AWS Identity and Access Management (IAM) es un servicio web que ayuda a controlar de forma segura el acceso de los usuarios a los recursos de AWS. Utilice IAM para controlar quién puede usar los recursos de AWS (autenticación), así como el modo en que pueden utilizarlos (autorización).
Puede conceder permiso a otras personas para administrar y utilizar los recursos de su cuenta de AWS sin tener que compartir su contraseña o clave de acceso.

# Servicio thingShadow 
 Thing Shadows permite que las aplicaciones y los dispositivos sincronicen su estado en la plataforma AWS IoT. Por ejemplo, un dispositivo remoto puede actualizar su Thing Shadow en AWS IoT, lo que permite al usuario ver el último estado del dispositivo a través de una aplicación móvil.

> :memo: **Note:** Device Shadow es un Json  para almacenar y recuperar el estado de un dispositivo.


# Amazon API Gateway
Amazon API Gateway es un servicio totalmente administrado que facilita a los desarrolladores la creación, la publicación, el mantenimiento, la monitorización y la protección de API a cualquier escala. Con Amazon API Gateway, puede crear una API personalizada de manera rápida y sencilla para el código ejecutado en AWS Lambda y, a continuación, llamar a dicho código de Lambda desde la API.

# Amazon Elastic Compute Cloud (Amazon EC2)
Arrancar nuevas instancias de servidor en cuestión de minutos, Amazon EC2 les brinda a los desarrolladores las herramientas necesarias para crear aplicaciones resistentes a errores y para aislarlas de los casos de error comunes. Con servicio Amazon Elastic Compute Cloud tendrás recursos informáticos escalables basados en web y gestionados con una metodología de alta calidad.

Se tiene acceso desde consola de Amazon EC2, AWS CLI,


# Endpoint
el Endpoint es la URL a la que una aplicación cliente puede acceder a su servicio. El mismo servicio web puede tener múltiples Endpoint, por ejemplo, para hacerlo disponible usando diferentes protocolos.

# DevOps
DevOps (acrónimo inglés de development -desarrollo- y operations -operaciones-) es una práctica de ingeniería de software que tiene como objetivo unificar el desarrollo de software (Dev) y la operación del software (Ops).
	
# Amazon Web Services AWS Lambda
 es un servicio de informática sin servidores que ejecuta el código como respuesta a eventos y administra automáticamente los recursos informáticos subyacentes. Puede usar AWS Lambda para ampliar otros productos de AWS con lógica personalizada o puede crear sus propios servicios back-end para que administren la seguridad, el rendimiento y el escalado de AWS. AWS Lambda puede ejecutar código automáticamente en respuesta a varios eventos, como solicitudes HTTP a través de Amazon API Gateway, modificaciones a objetos en buckets de Amazon S3, actualizaciones de tablas en Amazon DynamoDB y transiciones de estado en AWS Step Functions.

# AWS Rule Engine / 
El motor de reglas AWS IoT escucha los mensajes MQTT de entrada que coinciden con una regla. ”. invoca una función Lambda o envía un mensaje a un tema de Amazon (SNS). Las reglas de AWS IoT se componen de un filtro de temas, una acción de regla y, en la mayoría de los casos, un rol de IAM. Los mensajes publicados en temas que coinciden con el filtro de temas activan la regla. El rol de IAM contiene una o varias políticas de IAM que determinan a qué servicios de AWS puede tener acceso la regla. Puede crear varias reglas que escuchan un único tema.


# Amazon Web Services AWS SNS (Amazon Simple Notification Service)
 es un servicio de notificaciones móviles y mensajes de publicación/suscripción completamente administrado para coordinar la entrega de mensajes a clientes y puntos de conexión suscritos. Con SNS, puede distribuir mensajes a una gran cantidad de suscriptores, incluidos servicios y sistemas distribuidos, y dispositivos móviles
https://aws.amazon.com/es/sns/

# AWS Greengrass
 Es software que le permite ejecutar capacidades de informática local, mensajería, almacenamiento de datos en caché y sincronización para dispositivos conectados de manera segura. Con AWS Greengrass, los dispositivos conectados pueden ejecutar funciones de AWS Lambda, mantener los datos de dispositivos sincronizados y comunicarse con otros dispositivos de manera segura, incluso sin estar conectados a Internet. Con AWS Lambda, Greengrass se asegura de que sus dispositivos de IoT pueden responder con rapidez a eventos locales, operar con conexiones intermitentes y minimizar el costo de transmitir datos de IoT a la nube.

En concreto, AWS Greengrass permite la administración basada en la nube de aplicaciones que pueden implementarse para ejecutarse localmente (SIN UN SERVIDOR)…

## Notas:
Bróker es un intermediario<br>
Broadcast es un emisor<br>
Amazon Simple Storage Service (Amazon S3)<br>
Amazon Elastic Compute Cloud (Amazon EC2)<br>
SHADOW STATE ¿??????<br>
SHADOW METADETA??????????<br>
AMAZON LIGHTSAIL<br>
Instancias  en Amazon: son maquinas virtuales<br>


---
Copyright &copy; 2022 [carjavi](https://github.com/carjavi). <br>
```www.instintodigital.net``` <br>
carjavi@hotmail.com <br>
<p align="center">
    <a href="https://instintodigital.net/" target="_blank"><img src="https://raw.githubusercontent.com/carjavi/aws-guide/master/img/developer.png" height="100" alt="www.instintodigital.net"></a>
</p>