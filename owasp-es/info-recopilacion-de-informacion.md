---
description: Recopilar la mayor cantidad de información posible sobre la aplicación
---

# \[INFO\] RECOPILACIÓN DE INFORMACIÓN

### INFO-001 Fugas de información indexadas por buscadores

🎯 **Objetivo**

Buscar información sobre la aplicación en motores de búsqueda y redes sociales.

📝 **Pruebas**

* [ ] Buscar información sobre la aplicación en Google, Bing, GitHub, Shodan, Censys, Pastebin, Hunter, LinkedIn, Facebook y Twitter.
* [ ] Comprobar fugas de información en leaks.
* [ ] Lanzar waybackurls.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Conduct\_search\_engine\_discovery/reconnaissance\_for\_information\_leakage\_\(OTG-INFO-001\)](https://www.owasp.org/index.php/Conduct_search_engine_discovery/reconnaissance_for_information_leakage_%28OTG-INFO-001%29)
* [https://fortinux.gitbooks.io/humble\_tips/usando\_la\_linea\_de\_comandos/tutorial\_usar\_grep\_para\_buscar\_texto\_dentro\_de\_archivos\_en\_gnulinux.html](https://fortinux.gitbooks.io/humble_tips/usando_la_linea_de_comandos/tutorial_usar_grep_para_buscar_texto_dentro_de_archivos_en_gnulinux.html)

### INFO-002 Fingerprinting del servidor web

🎯 **Objetivo**

Buscar información sobre el servidor web, principalmente intentaremos conocer la versión y tipo del servidor web para buscar posibles vulnerabilidades y exploits.

📝 **Pruebas**

* [ ] Navegar por la aplicación y observar cabeceras.
* [ ] Analizar el código HTML.
* [ ] Observar las cookies.
* [ ] Lanzar Wappalyzer.
* [ ] Lanzar Whatweb.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Fingerprint\_Web\_Server\_\(OTG-INFO-002\)](https://www.owasp.org/index.php/Fingerprint_Web_Server_%28OTG-INFO-002%29)

### INFO-003 Fugas de información sensible en metaficheros del servidor

🎯 **Objetivo**

Buscar archivos o directorios que puedan contener información interesante o sensible.

📝 **Pruebas**

* [ ] Fuzz de directorios y archivos conocidos.
* [ ] Observar el tag HTML `META`.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Review\_Webserver\_Metafiles\_for\_Information\_Leakage\_\(OTG-INFO-003\)](https://www.owasp.org/index.php/Review_Webserver_Metafiles_for_Information_Leakage_%28OTG-INFO-003%29)

### INFO-004 Enumeración de aplicaciones en el servidor web

🎯 **Objetivo**

Enumerar las aplicaciones dentro del alcance de la auditoría y presentes en el mismo servidor \(Host compartido\), descubrimiento de puertos abiertos, servicios, subdominios o frameworks utilizados.

📝 **Pruebas**

* [ ] Utilizar BING con el filtro `IP:`.
* [ ] Enumeración de subdominios.
* [ ] Comprobar en `http://ipv4info.com`.
* [ ] Lanzar Nmap.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Enumerate\_Applications\_on\_Webserver\_\(OTG-INFO-004\)](https://www.owasp.org/index.php/Enumerate_Applications_on_Webserver_%28OTG-INFO-004%29)

### INFO-005 Fugas de información sensible en metadatos y comentarios

🎯 **Objetivo**

Buscar fugas de información en comentarios HTML y metadatos de archivos subidos al servidor.

📝 **Pruebas**

* [ ] Revisar código HTML.
* [ ] Extraer y analizar los metadatos de los archivos accesibles subidos al servidor con FOCA.
* [ ] Plugin Burp Suite: `Exiftool`.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Review\_webpage\_comments\_and\_metadata\_for\_information\_leakage\_\(OTG-INFO-005\)](https://www.owasp.org/index.php/Review_webpage_comments_and_metadata_for_information_leakage_%28OTG-INFO-005%29)

### INFO-006 Identificación de puntos de entrada en la aplicación

🎯 **Objetivo**

Comprender como se forman las peticiones y respuestas de la aplicación y buscar puntos de entrada.

📝 **Pruebas**

* [ ] Comprender como están formadas las peticiones y respuestas.
* [ ] Identificar en que puntos de la aplicación se usan los métodos POST y GET.
* [ ] Conocer los parámetros que usa la aplicación y con que fin son usados.
* [ ] Identificar que peticiones POST pueden ser cambiadas por GET \(longitud de respuesta similar\).
* [ ] Buscar formularios u otros posibles puntos de entrada para posteriormente buscar vulnerabilidades XSS o SQLi.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Identify\_application\_entry\_points\_\(OTG-INFO-006\)](https://www.owasp.org/index.php/Identify_application_entry_points_%28OTG-INFO-006%29)

### INFO-007 Mapas de rutas de ejecución a través de la aplicación

🎯 **Objetivo**

Crear un mapa de la aplicación y entender los flujos de trabajo.

📝 **Pruebas**

* [ ] Pasar la aplicación por Burp y navegar por ella.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Map\_execution\_paths\_through\_application\_\(OTG-INFO-007\)](https://www.owasp.org/index.php/Map_execution_paths_through_application_%28OTG-INFO-007%29)

### INFO-008 Fingerprinting del framework de la aplicación web

🎯 **Objetivo**

Conocer los distintos frameworks usados por la aplicación.

📝 **Pruebas**

* [ ] Analizar las cabeceras de respuesta del servidor de la aplicación, cookies, extensiones de los archivos, errores o comentarios en el HTML para identificar posibles frameworks utilizados en su desarrollo.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Fingerprint\_Web\_Application\_Framework\_\(OTG-INFO-008\)](https://www.owasp.org/index.php/Fingerprint_Web_Application_Framework_%28OTG-INFO-008%29)

### INFO-009 Fingerprinting de la aplicación web

🎯 **Objetivo**

Identificar las versiones de los frameworks, servidor web, tecnologías o librerías, para determinar como la aplicación puede verse afectada por vulnerabilidades conocidas.

📝 **Pruebas**

* [ ] Analizar las cabeceras y cookies.
* [ ] Revisar código fuente HTML.
* [ ] Revisar el archivo `robots.txt`.
* [ ] Lanzar WPScan o Joomscan \(si usa este framework\)
* [ ] Usar `https://builtwith.com/detailed/[TARGET]`.

🌐 **Referencias**

* [https://www.owasp.org/index.php/Fingerprint\_Web\_Application\_\(OTG-INFO-009\)](https://www.owasp.org/index.php/Fingerprint_Web_Application_%28OTG-INFO-009%29)

### INFO-010 Mapa de arquitectura de la aplicación

🎯 **Objetivo**

Conocer la infraestructura de la aplicación.

📝 **Pruebas**

* [ ] Buscar información referente a si existe un único servidor o más de uno.
* [ ] Conocer si existe un Balanceador, WAR, Firewall, etc.
* [ ] Cambiar las peticiones entre HTTP 1.0 y HTTP 1.1 con y sin host o intentando forzar errores.
* [ ] En HTTP 1.0 se pueden hacer peticiones sin host, podemos obtener información en las cabeceras de respuestas.
* [ ] Lanzar Whatwaff

🌐 **Referencias**

* [https://www.owasp.org/index.php/Map\_Application\_Architecture\_\(OTG-INFO-010\)](https://www.owasp.org/index.php/Map_Application_Architecture_%28OTG-INFO-010%29)

