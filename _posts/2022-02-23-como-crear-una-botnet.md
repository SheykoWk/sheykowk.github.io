---
layout: post
title:  "Como crear una Botnet"
date:   2022-02-23
excerpt: "Te explico de manera detallada como crear una botnet con UFONet :D."
tag:
- Español 
- Ciberseguridad
- Tutorial
- Documentacion
- DoS
- DDoS
feature: "https://i.imgur.com/1lYdckP.png"
comments: true
---

# Como montar una botnet con UFONet?

### **Para uso educativo** 

Antes de iniciar este post, hago un disclaimer de lo que el lector pueda hacer con la informacion aqui mostrada, esto es con fin meramente educativo y que conozcan la manera en la que se hacen los ataques DoS y DDoS

<figure>
	<img src="https://i.imgur.com/Kco7lCg.png">
	<figcaption>Version GUI de UFONet.</figcaption>
</figure>

# Introducción

UFONet se ejecuta en diversas plataformas. Requiere Python (>=3) y las siguientes bibliotecas:

{% highlight bash %}
python3-pycurl - Enlaces de Python a libcurl (Python 3)
python3-geoip - Enlaces de Python para la libreria de resolucion de ip a país con GeoIP
libgeoip-dev - Archivos de desarrollo para la libreria GeoIP
libgeoip1 - Libreria de resolucion de IP que no es DNS
python3-whois - Modulo de Python para recuperar información WHOIS - Python 3
python3-crypto - Algorittmos y protocolos criptográficos para Python
python3-requests - Libreria HTTP elegante y simple para Python 3
python3-scapy - Herramienta de seguridad de elaboracion / manipulacion / visualizacion de paquetes
{% endhighlight %}

Clonamos el repositorio en local.

{% highlight bash %}
git clone https://github.com/epsylon/ufonet.git
cd ufonet
{% endhighlight %}

Se pueden descargar automaticamente todas las bibliotecas requeridas usando (como root):

{% highlight bash %}
python3 setup.py install
{% endhighlight %}

O se puede instalar manualmente, en sistemas basados en Debian, ejecutando:

{% highlight bash %}
sudo apt-get install python3-pycurl python3-geoip python3-whois python3-crypto python3-requests python3-scapy libgeoip1 libgeoip-dev
{% endhighlight %}

En otros sistemas como: Kali, Arch, ParrotSec, Fedora, Red hat, Centos, etc... tambien ejecute:

{% highlight bash %}

pip3 install GeoIP
pip3 install python-geoip
pip3 install pygeoip
pip3 install requests
pip3 install pycrypto
pip3 install pycurl
pip3 install whois
pip3 install scapy-python3

{% endhighlight %}

Origen de las librerias :

* Python: <a href="https://www.python.org/downloads/">https://www.python.org/downloads/</a>
* PyCurl: <a href="http://pycurl.sourceforge.net/">http://pycurl.sourceforge.net/</a>
* GeoIP: <a href="https://pypi.python.org/pypi/GeoIP/">https://pypi.python.org/pypi/GeoIP/</a>
* Python-geoip: <a href="https://pypi.org/project/python-geoip/">https://pypi.org/project/python-geoip/</a>
* Pygeoip: <a href="https://pypi.org/project/pygeoip/">https://pypi.org/project/pygeoip/</a>
* Whois: <a href="https://pypi.python.org/pypi/whois">https://pypi.python.org/pypi/whois</a>
* PyCrypto: <a href="https://pypi.python.org/pypi/pycrypto">https://pypi.python.org/pypi/pycrypto</a>
* PyRequests: <a href="https://pypi.python.org/pypi/requests">https://pypi.python.org/pypi/requests</a>
* Scapy-Python3: <a href="https://pypi.org/project/scapy-python3/">https://pypi.org/project/scapy-python3/</a>
* Leaflet: <a href="http://leafletjs.com/ ">http://leafletjs.com/ </a> (provided)


## Introducción a la herramienta
UFONet es un software libre, P2P y  criptográfico que permite realizar ataques de denegacion de servicios (DoS) y de denegacion distribuida de servicios (DDoS), en la capa 7 , APP/HTTP (del **Open Systems Interconnection model** ) mediante la explotacion de una vulnerabilidad Open Redirect en sitios web de terceros para asi actuar como botner en la capa 3 (Red) abusando del protocolo.

Tambien funciona como una DarkNET encriptada para publicar y recibir contenido mediante la creacion de una red globar cliente / servidor.

<figure>
	<img src="https://i.imgur.com/lLHWDKI.png">
	<figcaption>El uso de este herramienta para atacar objetivos sin previo consentimiento es una practica ilegal.</figcaption>
</figure>

## Cómo se utiliza?

El uso de esta herramienta es con el siguiente comando:

{% highlight bash %}

./ufonet {options}

{% endhighlight %}

## Opciones

## Common Flags

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| --version   |    | muestra el número de versión del programa   |
|----
| --help   | -h   | Muestra este mensaje de ayuda   |
|----
| --verbose   |    | muestra el número de versión del programa   |
|----
| --version   |  -v  | activa verbose en las solicitudes   |
|----
| --examples   |    | imprime algunos ejemplos   |
|----
| --timeline   |    |  muestra la línea de tiempo del código del programa  |
|----
| --update   |    |  la comprobación de la última versión estable  |
|----
| --check-tor   |    |  comprueba si Tor esta correctamente instalado  |
|----
| --force-ssl   |    |  fuerza el uso de solicitudes SSL/HTTPS  |
|----
| --force-yes   |    |  establezca 'SÍ' en todas las preguntas  |
|----
| --gui   |    |  Activa la interfaz grafica en el puerto 9999  
{: rules="groups"}

## Herramientas

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| --crypter   |    | Cifrar/descifrar mensajes usando AES256+HMAC-SHA1   |
|----
| --network   |  | Mostrar información sobre su red (MAC, IP’s)   |
|----
| --xray=XRAY   |    | Escáner de puerto rápido (por ejemplo: --xray 'http(s)://target-com')   |
|----
| --xray-ps=XRAYPS   |    | Establecer rango de puertos para escanear (por ejemplo: --xray-ps '1-1024')
{: rules="groups"}

## Configuració de las peticiones

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| --proxy=PROXY   |    | Usar servidor proxy (por ejemplo: - -proxy 'http://127.0.0.1:8118')   |
|----
| --user-agent=AGENT   |  | Use otro encabezado HTTP User-Agent (predeterminado: SPOOFED)   |
|----
| --referer=REFERER   |    | Use otro encabezado HTTP Referer (predeterminado: SPOOFED)   |
|----
| --host=HOST   |    | Use otro encabezado de host HTTP (predeterminado: NINGUNO) |
| --xforw   |    |  Configure su HTTP X-Forwarded-For con valores de IP aleatorios  |
|----
| --xclient   |    |  Establezca su HTTP X-Client-IP con valores de IP aleatorios  |
|----
| --timeout=TIMEOUT   |    |  Seleccione su tiempo de espera (predeterminado: 5)  |
|----
| --retries=RETRIES   |    |  Reintenta cuando la conexión se agota (predeterminado: 0)  |
|----
| --threads=THREADS   |    |  Número máximo de solicitudes HTTP concurrentes (predeterminado: 5)  |
|----
| --delay=DELAY   |    |    Retraso entre cada solicitud HTTP (predeterminado: 0)
{: rules="groups"}

## Busqueda de Zombies

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| --auto-search   |    | Buscar automáticamente 'zombies' (¡puede llevar tiempo!)   |
|----
| -s   | -s | Busca desde un “dork” (ej.: -s 'proxy.php?url=')   |
|----
| --sd=DORKS   |    |  Buscar desde el archivo 'dorks' (ej.: --sd 'botnet/dorks.txt')   |
|----
| --sn=RESULTS   |    | Establecer el número máximo de resultados para el motor (predeterminado: 10) |
|----
| --se=ENGINE   |    |  Motor de búsqueda para 'dorking' (predeterminado: DuckDuckGo)  |
|----
| --sa   |    |  Buscar masivamente usando todos los motores (¡puede tomar tiempo!)  |
|----
| —sax=ENGINE   |    |  Excluye motores cuando se realizan búsquedas masivas (por ejemplo: 'Bing,Yahoo')  
{: rules="groups"}

## Probar la botnet

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| --test-offline   |    | Comprobación rápida para descartar bots fuera de línea  |
|----
| --test-all   |  | Actualizar TODO el estado de botnet (puede llevar tiempo!) |
|----
| -t   |  -t  |  Actualizar el estado de 'zombies' (por ejemplo: -t 'botnet/zombies.txt' )   |
|----
| --attack-me |    | Ordene a los 'zombis' que lo ataquen (se requiere NAT!)  
{: rules="groups"}

## Comunidad

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| --deploy   |    | Implemente datos para compartir en ' /var/www/ufonet/'  |
|----
| --grider   |  | Crear un 'grider' para compartir 'estadísticas/juegos de guerra/mensajes' |
|----
| --black-hole  |   |  Generar un 'agujero negro' para compartir 'zombis' |
|----
| --up-to=UPIP |    | Subir 'zombies' a IP (ej: --up- para '255.255.1.1') |
|----
| --down-to=DIP |    | Subir 'zombies' a IP (ej: --up- para '255.255.1.1') | 
|----
| --upload-zombies |    | Subir 'zombies' a la comunidad | 
|----
| --udownload-zombies |    | Descargar 'zombies' a la comunidad | 
|----
| --upload-github |    | Subir 'zombies' a GitHub | 
|----
| --download |    | Descargar 'zombies' de GitHub 
{: rules="groups"}

## Objetivo de investigacion

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| -i   |  -i  | Buscar el archivo más grande (por ejemplo: -i 'http(s)://target.com')  |
|----
| -x   | -x | Examinar la configuración del servidor web (+CVE, +detección WAF) 
{: rules="groups"}

## Configuracion de ataques

| Opción | Versión corta | Descripcion |
|:--------|:-------:|--------:|
| -a  TARGET |  -a  | [DDoS] ataca un objetivo (ej: -a 'http(s)://target.com')  |
|----
| -f TARGET_LIST | -f | [DDoS] ataca una lista de objetivos (ej: -f 'targets.txt') |
|----
| -b  PLACE |  -b  |  Set lugar para atacar (ej: -b '/path/big.jpg')   |
|----
| -r ROUNDS |  -r  | Establece el número de rondas (por ejemplo: -r '1000') (predeterminado: 1)
{: rules="groups"}
