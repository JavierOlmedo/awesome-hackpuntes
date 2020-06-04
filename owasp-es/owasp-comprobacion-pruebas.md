---
description: Listado de pruebas de OWASP
---

# OWASP: Guía de pruebas

{% file src="../.gitbook/assets/owasp\_checklist\_20200604.xlsx" caption="OWASP Checklist ES" %}

♻️ **4 de junio de 2020**

### \[INFO\] RECOPILACIÓN DE INFORMACIÓN

* [ ] INFO-01 Fugas de información indexadas por buscadores
* [ ] INFO-02 Fingerprinting del servidor web
* [ ] INFO-03 Fugas de información sensible en metaficheros del servidor
* [ ] INFO-04 Enumeración de aplicaciones en el servidor web
* [ ] INFO-05 Fugas de información sensible en metadatos y comentarios
* [ ] INFO-06 Identificación de puntos de entrada en la aplicación
* [ ] INFO-07 Mapas de rutas de ejecución a través de la aplicación
* [ ] INFO-08 & INFO-09 Fingerprinting de la aplicación web
* [ ] INFO-10 Mapa de arquitectura de la aplicación

### \[CONFIG\] GESTIÓN DE CONFIGURACIÓN E IMPLEMENTACIÓN

* [ ] CONFIG-01 Configuración de infraestructura/red
* [ ] CONFIG-02 Configuración de la plataforma de la aplicación
* [ ] CONFIG-03 Fugas de información sensible en el manejo de extensiones de archivos
* [ ] CONFIG-04 Fugas de información sensible en archivos obsoletos, de backup o no referenciados
* [ ] CONFIG-05 Enumeración de infraestructura e interfaces de administración de la aplicación
* [ ] CONFIG-06 Métodos HTTP
* [ ] CONFIG-07 HTTP Strict Transport Security
* [ ] CONFIG-08 Política de dominio cruzado RIA
* [ ] CONFIG-09 Permisos de archivos
* [ ] CONFIG-10 Toma de control de subdominio
* [ ] CONFIG-11 Almacenamiento en la nube

### \[IDENT\] GESTIÓN DE IDENTIDADES

* [ ] IDENT-001 Definición de roles
* [ ] IDENT-002 Proceso de registro
* [ ] IDENT-003 Proceso de asignación de cuentas de usuario
* [ ] IDENT-004 Enumeración de cuentas de usuario
* [ ] IDENT-005 Política de nombres de usuario débil

### \[AUTHN\] AUTENTICACIÓN

* [ ] AUTHN-01 Transporte de credenciales por canales cifrados
* [ ] AUTHN-02 Uso de credenciales por defecto
* [ ] AUTHN-03 Debilidades en el mecanismo de bloqueo
* [ ] AUTHN-04 Fallos en el esquema de autenticación
* [ ] AUTHN-05 Sistema recuérdame
* [ ] AUTHN-06 Debilidades en la caché del navegador
* [ ] AUTHN-07 Política de contraseñas débiles
* [ ] AUTHN-08 Debilidades en el sistema de pregunta de seguridad
* [ ] AUTHN-09 Debilidades en las funcionalidades de cambio y reseteo de contraseñas
* [ ] AUTHN-10 Canales alternativos de autenticación

### \[AUTHZ\] AUTORIZACIÓN

* [ ] AUTHZ-01 Política de contraseñas débiles
* [ ] AUTHZ-02 Fallos en el control de acceso a recursos y funcionalidades
* [ ] AUTHZ-03 Escalado de privilegios
* [ ] AUTHZ-04 Referencias directas inseguras a objetos

### \[SESS\] GESTIÓN DE SESIONES

* [ ] SESS-001 Fallos en el sistema de manejo de sesiones
* [ ] SESS-002 Atributos de las cookies
* [ ] SESS-003 Fijación de sesión
* [ ] SESS-004 Variables de sesión expuestas
* [ ] SESS-005 Cross Site Request Forgery \(CSRF\)
* [ ] SESS-006 Sistema de cierre de sesión
* [ ] SESS-007 Sistema de timeout \(caducidad\) de la sesión
* [ ] SESS-008 Sobrecarga de variables de sesión \(Session Puzzling\)

### \[INPVAL\] VALIDACIÓN DE ENTRADA

* [ ] INPVAL-01 Cross Site Scripting reflejado
* [ ] INPVAL-02 Cross Site Scripting almacenado
* [ ] INPVAL-03 Manipulación de verbos HTTP
* [ ] INPVAL-04 Contaminación de parámetros HTTP
* [ ] INPVAL-05 Inyección SQL
* [ ] INPVAL-06 Inyección LDAP
* [ ] INPVAL-07 Inyección XML
* [ ] INPVAL-08 Inyección SSI
* [ ] INPVAL-09 Inyección Xpath
* [ ] INPVAL-10 Inyección IMAP/SMTP
* [ ] INPVAL-11 Inyección de código
* [ ] INPVAL-12 Inyección de comandos
* [ ] INPVAL-13 Sobrecargas de buffer
* [ ] INPVAL-14 Vulnerabilidades incubadas
* [ ] INPVAL-15 HTTP Splitting/Smuggling
* [ ] INPVAL-16 HTTP solicitudes entrantes
* [ ] INPVAL-17 Inyección en cabecera Host
* [ ] INPVAL-18 Inyección de plantilla del lado del servidor \(SSTI\)

### \[ERR\] MANEJO DE ERRORES

* [ ] ERR-01 Análisis de códigos de error
* [ ] ERR-02 Análisis de trazas de error

### \[CRYPST\] CRIPTOGRAFÍA

* [ ] CRYPST-01 Confidencialidad de la información en tránsito
* [ ] CRYPST-02 Padding Oracle
* [ ] CRYPST-03 Envío de información sensible por canales sin cifrar
* [ ] CRYPST-04 Cifrado débil

### \[BUSLOGIC\] LÓGICA DE NEGOCIO

* [ ] BUSLOGIC-01 Validación de datos de la lógica del negocio   
* [ ] BUSLOGIC-02 Habilidad de manipulación consultas
* [ ] BUSLOGIC-03 Comprobación de integridad 
* [ ] BUSLOGIC-04 Tiempo de procesamiento
* [ ] BUSLOGIC-05 Límite de veces de uso de una función
* [ ] BUSLOGIC-06 Evasión de los flujos de trabajo
* [ ] BUSLOGIC-07 Defensas contra el mal uso de la aplicación
* [ ] BUSLOGIC-08 Subida de tipos de archivos inesperados
* [ ] BUSLOGIC-09 Subida de archivos maliciosos

### \[CLIENT\] PRUEBAS DEL LADO DEL CLIENTE

* [ ] CLIENT-01 Cross Site Scripting basado en DOM
* [ ] CLIENT-02 Ejecución de JavaScript
* [ ] CLIENT-03 Inyección de HTML
* [ ] CLIENT-04 Redireccionamiento de la URL del lado del cliente
* [ ] CLIENT-05 Pruebas de inyección de CSS
* [ ] CLIENT-06 Pruebas de la manipulación de recursos del lado del cliente
* [ ] CLIENT-07 Intercambio de recursos de origen cruzado
* [ ] CLIENT-08 Pruebas de Cross Site Flashing 
* [ ] CLIENT-09 Clickjacking
* [ ] CLIENT-10 WebSockets
* [ ] CLIENT-11 Mensajería web
* [ ] CLIENT-12 Almacenamiento local
* [ ] CLIENT-13 Cross-Site Script Inclusion \(XSSI\)

