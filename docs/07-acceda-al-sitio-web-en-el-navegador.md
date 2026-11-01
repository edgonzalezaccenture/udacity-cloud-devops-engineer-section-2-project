# Acceda al sitio web en el navegador web

El nombre de dominio exacto y las URL de S3 serán diferentes en tu caso.

1. Abre un navegador como Google Chrome y pega el nombre de dominio de CloudFront que copiaste (por ejemplo, `dgf7z6g067r6d.cloudfront.net`) sin añadir `/index.html` al final. Debe mostrarse la página de inicio predeterminada.
2. Accede al sitio a través del punto de enlace del sitio web, por ejemplo `http://<bucket-name>.s3-website.us-east-2.amazonaws.com/`.
3. Accede al objeto a través de su URL de S3, por ejemplo `https://<bucket-name>.s3.amazonaws.com/index.html`.

Los tres enlaces (nombre de dominio de CloudFront, URL del objeto de S3 y punto de enlace del sitio web) muestran el mismo contenido de `index.html`.

Si no estuviéramos alojando el sitio en S3, el bucket podría ser privado y el contenido se serviría solo a través del nombre de dominio de CloudFront. En ese caso, no se podría acceder al contenido privado con la URL del objeto de S3 ni con el punto de enlace del sitio web.

## Solución de problemas

Si al terminar no ves el contenido del sitio, el curso remite a dos guías de AWS:

- "Estoy usando un punto final del sitio web S3 como origen de mi distribución CloudFront. ¿Por qué recibo errores 403 de acceso denegado?"
- El tutorial oficial "Uso de un punto final del sitio web como origen, con acceso anónimo (público) permitido".

Comprueba que la distribución usa el dominio correcto: debe ser el punto de enlace del alojamiento estático, con la forma `<bucket-name>.s3-website-region.amazonaws.com`.
