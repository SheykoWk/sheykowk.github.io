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

### *para uso educativo* 

Antes de iniciar este post, hago un disclaimer de lo que el lector pueda hacer con la informacion aqui mostrada, esto es con fin meramente educativo y que conozcan la manera en la que se hacen los ataques DoS y DDoS

<figure>
	<a href="https://i.imgur.com/Kco7lCg.png"><img src="https://i.imgur.com/Kco7lCg.png"></a>
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
