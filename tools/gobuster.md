# Gobuster

* `dir` Modo fuzz
* `dns` Búsqueda de subdominios por fuerza bruta
* `-u <TARGET>` Especificar el objetivo
* `-w <PATH>` Ruta del diccionario a utilizar
* `-t <INT>` Número de hilos a lanzar
* `-p http://<IP>:<PORT>` Usar proxy
* `-x <EXTENSION>` Añadir comprobación de extensiones, puede añadirse varias si separamos por comas \(php,txt,html\)
* `-k` Permitir conexiones inseguras, ignorando CAs
* `-r` Seguir redirección
* `-e` Imprime la URL completa
* `-c` Expecifica la cookie
  * Realizar fuzzing de archivos con extensiones php, txt y html, seguir redirecciones, imprimir ruta completa y pasar por el proxy ignorando certificados

    ```text
    gobuster dir -u https://<TARGET>/ -w <PATH> -x php,txt,html -t 23 -p http://localhost:8080 -k -r -e
    ```

    Adicionalmente podemos añadir `| tee gobuster.txt` al final para guardar la salida en un archivo de texto.



