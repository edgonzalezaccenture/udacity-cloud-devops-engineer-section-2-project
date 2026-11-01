# Proyecto: sitio web estático en S3 y CloudFront (Udacity Cloud DevOps Engineer, sección 2)

Proyecto de la sección 2 del Nanodegree **Cloud DevOps Engineer** («Ingeniero de DevOps en la nube», nd9991) de Udacity.

**Reto:** alojar un sitio web estático en un bucket S3 y servirlo a través de la CDN de CloudFront.

## Documentación

Documentación de la formación, en el mismo orden en que aparece en el curso:

| Archivo | Qué es |
|---|---|
| [docs/01-introduccion.md](docs/01-introduccion.md) | Introducción: los dos objetivos del proyecto (alojar el sitio en S3 y servirlo con CloudFront), la diferencia entre bucket público y privado con OAC/OAI, qué hay que hacer paso a paso, el código de inicio y los temas tratados. |
| [docs/02-crear-bucket-s3.md](docs/02-crear-bucket-s3.md) | Crear el bucket S3: los pasos en la consola de AWS, la convención de nombres con el ID de cuenta, desactivar Bloquear acceso público, por qué se permite la lectura pública y qué revisar si aparece `AccessDenied`. |
| [docs/03-subir-archivos-a-s3-bucket.md](docs/03-subir-archivos-a-s3-bucket.md) | Subir el sitio al bucket: `index.html` y las carpetas `css`, `img` y `vendor` sin la carpeta principal, y qué hacer si la carga falla (bloqueador de anuncios o cortafuegos, con la alternativa de la CLI de AWS) o si hay demasiados archivos (subir el zip y descomprimirlo con CloudShell). |
| [docs/04-politica-del-bucket.md](docs/04-politica-del-bucket.md) | Política del bucket: la política JSON que permite `s3:GetObject` a todos, dónde escribirla en la pestaña Permisos y por qué un bucket privado con CloudFront no necesitaría escribirla a mano. |
| [docs/05-configure-s3-bucket.md](docs/05-configure-s3-bucket.md) | Configurar el bucket: activar el alojamiento de sitios web estáticos en Propiedades, usar `index.html` como página de inicio y de error, y copiar el punto de enlace del sitio. |
| [docs/06-distribute-website-via-cloudfront.md](docs/06-distribute-website-via-cloudfront.md) | Distribuir el sitio con CloudFront: crear la distribución con el punto de enlace del sitio como origen, los valores de cada campo, cuánto tarda en desplegarse y dónde copiar su URL. |
| [docs/07-acceda-al-sitio-web-en-el-navegador.md](docs/07-acceda-al-sitio-web-en-el-navegador.md) | Comprobar el sitio en el navegador: las tres URL que deben mostrar el mismo `index.html` (CloudFront, punto de enlace del sitio y objeto de S3) y qué revisar si aparece un error 403. |
| [docs/08-rubrica.md](docs/08-rubrica.md) | Rúbrica: los criterios de evaluación (archivos, distribución y acceso), lo que hay que entregar (captura del bucket, URL de CloudFront y del sitio) y las sugerencias para destacar. |
| [docs/09-presentacion.md](docs/09-presentacion.md) | Presentación: fecha límite (27 de noviembre de 2026), qué debe llevar la carpeta comprimida (capturas y `README.txt`), la lista de verificación y el recordatorio de borrar los recursos de AWS tras la aprobación. |
