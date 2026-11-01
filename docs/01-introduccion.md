# Introducción

## Descripción general del proyecto

La nube es perfecta para alojar sitios web estáticos: los que solo incluyen archivos HTML, CSS y JavaScript y no requieren procesamiento en el servidor. El proyecto tiene dos objetivos principales:

- Alojar un sitio web estático en S3.
- Acceder a las páginas web almacenadas en caché mediante la red de distribución de contenido (CDN) de CloudFront, que ofrece baja latencia y altas velocidades de transferencia.

El alojamiento de sitios web estáticos requiere esencialmente un bucket público, mientras que CloudFront puede funcionar con buckets públicos y privados.

## Nota importante sobre S3 y CloudFront

- El alojamiento estático tradicional de S3 requiere que los objetos del bucket sean de acceso público cuando se utiliza el punto de enlace del sitio web de S3.
- CloudFront se puede configurar para servir contenido desde un bucket privado con Origin Access Control (OAC) u Origin Access Identity (OAI). Es el enfoque recomendado y más seguro: el bucket sigue siendo privado y el contenido se entrega a través de la CDN.
- La configuración de S3 Block Public Access puede impedir el alojamiento público. Si se usa el punto de enlace del sitio web de S3, puede que haya que ajustarla o usar CloudFront con OAC en su lugar.

## Qué harás en este proyecto

1. Crear un bucket S3 y cargar los archivos del sitio web.
2. Configurar el bucket para alojamiento de sitios web estáticos, o configurar CloudFront para usarlo como origen privado con OAC/OAI.
3. Asegurar el acceso con políticas de bucket adecuadas u orígenes de CloudFront.
4. Crear una distribución de CloudFront para acelerar la entrega y, opcionalmente, configurar el almacenamiento en caché, el TTL y la invalidación.
5. Acceder al sitio web a través del punto de enlace de CloudFront o de un dominio personalizado que apunte a CloudFront.

## Requisitos previos

- Código de inicio para estudiantes: hay que descargarlo y descomprimirlo. El enlace está en la página del curso.

## Temas tratados

- Creación de un bucket S3.
- Configuración del bucket S3.
- Distribución de sitios web a través de CloudFront.
- Acceso al sitio web desde el navegador.
