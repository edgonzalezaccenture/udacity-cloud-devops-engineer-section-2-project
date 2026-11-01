# Distribute Website via CloudFront

1. En **Services**, arriba a la izquierda, busca "cloudfront" y selecciona **CloudFront**.
2. En el panel de CloudFront, haz clic en **Create Distribution**.
3. Crea la distribución con estos datos:

| Campo | Valor |
|---|---|
| Origin > Domain Name | No selecciones el bucket de la lista desplegable. Pega el punto de enlace del alojamiento estático, con la forma `<bucket-name>.s3-website-region.amazonaws.com` |
| Origin > Enable Origin Shield | No (es el valor por defecto) |
| Default cache behavior | Valores por defecto |
| Cache key and origin requests | Valores por defecto |

4. En la página siguiente, desactiva las protecciones de seguridad. Puede no ser buena idea en producción, pero el ejercicio lo mantiene simple.
5. Deja el resto de opciones por defecto y haz clic en **Create Distribution**. La distribución puede tardar hasta 10 minutos en crearse.
6. Cuando el estado pase de **In Progress** a **Deployed**, copia la URL de la distribución de la columna **Domain Name**. El ejemplo del curso es `d352j84q5aqktd.cloudfront.net`; la tuya será distinta.

En cuanto la distribución está en **Deployed**, se conecta a S3 y empieza a almacenar en caché las páginas. Esto puede tardar entre 10 y 30 minutos o más. Cuando termina, la URL de CloudFront deja de redirigir a la URL del objeto de S3.
