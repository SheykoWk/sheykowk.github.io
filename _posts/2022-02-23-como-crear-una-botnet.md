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
	<a href="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/c069af63-b6f8-4567-aaaf-b100050ae0ef/Inicio.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220225%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220225T034209Z&X-Amz-Expires=86400&X-Amz-Signature=638147110240f4d76807628241c8bae9d0fcb4b70f22dec131a81219ccbceec2&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Inicio.png%22&x-id=GetObject"><img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/c069af63-b6f8-4567-aaaf-b100050ae0ef/Inicio.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220225%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220225T034209Z&X-Amz-Expires=86400&X-Amz-Signature=638147110240f4d76807628241c8bae9d0fcb4b70f22dec131a81219ccbceec2&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Inicio.png%22&x-id=GetObject"></a>
	<figcaption>Version GUI de UFONet.</figcaption>
</figure>

# Introducción

UFONet se ejecuta en diversas plataformas. Requiere Python (>=3) y las siguientes bibliotecas:
```Bash
python3-pycurl - Enlaces de Python a libcurl (Python 3)
python3-geoip - Enlaces de Python para la libreria de resolucion de ip a país con GeoIP
libgeoip-dev - Archivos de desarrollo para la libreria GeoIP
libgeoip1 - Libreria de resolucion de IP que no es DNS
python3-whois - Modulo de Python para recuperar información WHOIS - Python 3
python3-crypto - Algorittmos y protocolos criptográficos para Python
python3-requests - Libreria HTTP elegante y simple para Python 3
python3-scapy - Herramienta de seguridad de elaboracion / manipulacion / visualizacion de paquetes
```

Clonamos el repositorio en local.

```Bash
git clone https://github.com/epsylon/ufonet.git
cd ufonet
```
