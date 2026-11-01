# Crear un bucket S3

1. En la consola de administración de AWS, escribe "S3" en el cuadro de búsqueda de servicios y selecciona **S3**. Comprueba antes que estás en la cuenta correcta y en la región deseada (arriba a la derecha).
2. En el panel de Amazon S3, haz clic en **Crear bucket**.
3. En la configuración general, escribe un nombre. Los nombres de bucket deben ser únicos en todo el mundo. Una convención práctica es `my-123456789-bucket`, sustituyendo `123456789` por tu ID de cuenta de AWS de 12 dígitos.
4. En **Bloquear acceso público**, si alojas un sitio web público estático, desmarca **Bloquear todo el acceso público** y confirma el aviso. AWS advierte sobre el acceso público: confirma solo si entiendes las implicaciones de seguridad.
5. Haz clic en **Crear bucket**.
6. Cuando esté creado, haz clic en su nombre para abrirlo y ver su configuración y contenido.

## Por qué se permite la lectura pública

Un sitio web estático necesita que los objetos sean legibles públicamente si se accede a ellos directamente por las URL de S3. Para sitios en producción es más seguro mantener el bucket privado y servir el contenido con CloudFront y Origin Access Control (OAC), porque así los objetos no se hacen públicos.

## Solución de problemas

Si ves `AccessDenied` al visitar el sitio, comprueba que:

- Bloquear acceso público está desactivado.
- Los objetos tienen permisos de lectura pública o hay una política de bucket que permite `GetObject`.
- La URL que pides coincide exactamente con el nombre de la clave del objeto (distingue entre mayúsculas y minúsculas).
