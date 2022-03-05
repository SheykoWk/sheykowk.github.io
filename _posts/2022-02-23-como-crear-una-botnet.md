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
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}

