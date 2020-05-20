---
description: >-
  Recopilar la mayor cantidad de información posible sobre la aplicación,
  sistema u organización.
---

# \[INFO\] RECOPILACIÓN DE INFORMACIÓN

### INFO-01 Fugas de información indexadas por buscadores

🎯 **Objetivo**

Buscar información sensible sobre la aplicación, sistema u organización que pueda estar expuesta tanto directamente \(en el sitio web de la organización\) o indirectamente \(sitio web de un tercero\).

📝 **Pruebas**

* [ ] Buscar información sobre la aplicación en Google, Bing, GitHub, Shodan, Censys, Pastebin, Hunter, LinkedIn, Facebook y Twitter.
* [ ] Comprobar fugas de información en leaks.
* [ ] Lanzar **waybackurls**.
* [ ] Comprobar emails en **hunter.io**.
* [ ] Comprobar dominio en **shodan.io**.
* [ ] Comprobar dominio en **binsearch.info**.

**Google**

```text
site:[DOMAIN]
cache:[DOMAIN]
filetype:[EXTENSION]
inurl:[DORK]
intext:[DORK]
inbody:[DORK]
intitle:[DORK]
```

**Archive**

```text
https://web.archive.org/web/*/[DOMAIN]/*
```

```text
waybackurls [DOMAIN] | tee -a [DOMAIN].txt
```

**Hunter.io**

```text
https://hunter.io/search/[DOMAIN]
```

**Shodan.io**

```text
https://www.shodan.io/search?query=[DOMAIN]
```

**Binsearch.info**

```text
https://binsearch.info/?q=[DOMAIN]
```

🌐 **Referencias**

* [OWASP GitHub INFO-01](https://github.com/OWASP/wstg/blob/master/document/4-Web_Application_Security_Testing/01-Information_Gathering/01-Conduct_Search_Engine_Discovery_Reconnaissance_for_Information_Leakage.md)
* [Google Hacking Database/](https://www.exploit-db.com/google-hacking-database/)

### INFO-02 Fingerprinting del servidor web

🎯 **Objetivo**

Buscar información sobre la versión y tipo del servidor web para buscar posibles vulnerabilidades y exploits.

📝 **Pruebas**

* [ ] Navegar por la aplicación y observar cabeceras.
* [ ] Analizar el código HTML.
* [ ] Observar las cookies.
* [ ] Lanzar **Wappalyzer**.
* [ ] Lanzar **Whatweb**.
* [ ] Lanzar **Netcraft**.

**Wappalyzer**

```text
wappalyzer [URL] --user-agent "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4135.1 Safari/537.36" --proxy "http://127.0.0.1:8080" --recursive --pretty >> [DOMAIN].json
```

**Whatweb**

```text
whatweb --aggression 4 --user-agent "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4135.1 Safari/537.36" --proxy "127.0.0.1:8080" --url-prefix "https://" [DOMAIN]
```

**Netcraft**

```text
https://sitereport.netcraft.com/?url=[URL]
```

🌐 **Referencias**

* [OWASP GitHub INFO-02](https://github.com/OWASP/wstg/blob/master/document/4-Web_Application_Security_Testing/01-Information_Gathering/02-Fingerprint_Web_Server.md)

### INFO-03 Fugas de información sensible en metaficheros del servidor

🎯 **Objetivo**

Buscar archivos o directorios que puedan contener información interesante o sensible.

📝 **Pruebas**

* [ ] Comprobar el archivo `robots.txt`.
* [ ] Observar el tag HTML `META`.
* [ ] Lanzar crawl con Burp Suite.
* [ ] Lanzar **gobuster** con directorios conocidos.
* [ ] Lanzar **wfuzz** con ficheros conocidos.

**Wget**

```text
wget [URL]/robots.txt
```

**Curl**

```text
curl -O [URL]/robots.txt
```

**Gobuster**

```text
gobuster -w "/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt" -t 23 dir -u "[URL]" -o directories.txt
```

```text
gobuster -w "/usr/share/wordlists/dirb/common.txt" -t 23 -x php,txt,html dir -u "[URL]" -o common_files.txt
```

**Wfuzz**

```text
wfuzz -c -t 23 -w "/usr/share/wordlists/dirb/common.txt" -z "php,txt,html" -u "[URL]FUZZ"
```

🌐 **Referencias**

* [OWASP GitHub INFO-03](https://github.com/OWASP/wstg/blob/master/document/4-Web_Application_Security_Testing/01-Information_Gathering/03-Review_Webserver_Metafiles_for_Information_Leakage.md)

### INFO-04 Enumeración de aplicaciones en el servidor web

🎯 **Objetivo**

Enumerar las aplicaciones dentro del alcance de la auditoria y presentes en el mismo servidor \(Host compartido\), descubrimiento de puertos abiertos, servicios, subdominios o frameworks utilizados.

📝 **Pruebas**

* [ ] Utilizar el motor de búsqueda **bing** con el filtro `IP:`.
* [ ] Comprobar en `http://ipv4info.com`.
* [ ] Lanzar **Nmap**.
* [ ] Lanzar **Wfuzz**.
* [ ] Lanzar **Assetfinder**.
* [ ] Lanzar **Amass**.
* [ ] Lanzar **Sublist3r**.

**Bing**

```text
https://www.bing.com/search?q=IP%3A[IP]
```

**IPv4info**

```text
http://ipv4info.com/search/[DOMAIN]
```

**Nmap**

```text
nmap -p- --open -T2 -v -oA ports [DOMAIN]
```

```text
nmap -sC -sV -T2 -v -oA services -p[PORTS] [DOMAIN]
```

**Wfuzz**

```text
wfuzz -c -t 23 -w "/usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-20000.txt" -H "Host: FUZZ.[DOMAIN]" -u "[URL]"
```

**Assetfinder**

```text
assetfinder --subs-only [DOMAIN] | tee -a assetfinder.txt
```

**Amass**

```text
amass enum -passive -d [DOMAIN] -o amass-pasive.txt
```

```text
amass enum -brute -d [DOMAIN] -o amass-brute.txt
```

**Sublist3r**

```text
python sublist3r.py -d [DOMAIN] -v -o sublister.txt
```

🌐 **Referencias**

* [OWASP GitHub INFO-04](https://github.com/OWASP/wstg/blob/master/document/4-Web_Application_Security_Testing/01-Information_Gathering/04-Enumerate_Applications_on_Webserver.md)

### INFO-005 Fugas de información sensible en metadatos y comentarios

🎯 **Objetivo**

Buscar fugas de información en comentarios HTML y metadatos de archivos subidos al servidor.

📝 **Pruebas**

* [ ] Revisar código HTML.
* [ ] Extraer y analizar los metadatos de los archivos accesibles subidos al servidor con FOCA.
* [ ] Plugin Burp Suite: `Exiftool`.

🌐 **Referencias**

* [OWASP GitHub INFO-005](https://github.com/OWASP/wstg/blob/master/document/4_Web_Application_Security_Testing/4.2_Information_Gathering/4.2.5_Review_Webpage_Comments_and_Metadata_for_Information_Leakage_OTG-INFO-005.md)

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

* [OWASP GitHub INFO-006](https://github.com/OWASP/wstg/blob/master/document/4_Web_Application_Security_Testing/4.2_Information_Gathering/4.2.6_Identify_Application_Entry_Points_OTG-INFO-006.md)

### INFO-007 Mapas de rutas de ejecución a través de la aplicación

🎯 **Objetivo**

Crear un mapa de la aplicación y entender los flujos de trabajo.

📝 **Pruebas**

* [ ] Pasar la aplicación por Burp y navegar por ella.

🌐 **Referencias**

* [OWASP GitHub INFO-007](https://github.com/OWASP/wstg/blob/master/document/4_Web_Application_Security_Testing/4.2_Information_Gathering/4.2.7_Map_Execution_Paths_Through_Application_OTG-INFO-007.md)

### INFO-008 Fingerprinting del framework de la aplicación web

🎯 **Objetivo**

Conocer los distintos frameworks usados por la aplicación.

📝 **Pruebas**

* [ ] Analizar las cabeceras de respuesta del servidor de la aplicación, cookies, extensiones de los archivos, errores o comentarios en el HTML para identificar posibles frameworks utilizados en su desarrollo.

🌐 **Referencias**

* [OWASP GitHub INFO-008](https://github.com/OWASP/wstg/blob/master/document/4_Web_Application_Security_Testing/4.2_Information_Gathering/4.2.8_Fingerprint_Web_Application_Framework_OTG-INFO-008.md)

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

* [OWASP GitHub INFO-009](https://github.com/OWASP/wstg/blob/master/document/4_Web_Application_Security_Testing/4.2_Information_Gathering/4.2.9_Fingerprint_Web_Application_OTG-INFO-009.md)

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

* [OWASP GitHub INFO-010](https://github.com/OWASP/wstg/blob/master/document/4_Web_Application_Security_Testing/4.2_Information_Gathering/4.2.10_Map_Application_Architecture_OTG-INFO-010.md)

