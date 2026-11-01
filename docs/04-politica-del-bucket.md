# Política del bucket

1. Abre la pestaña **Permisos** y comprueba que el bucket permite el acceso público.
2. La sección **Política de bucket** está vacía. Haz clic en **Editar**. Revisa esta política de nuevo después de configurar la distribución de CloudFront.
3. Escribe la siguiente política, sustituyendo `your-website` por el nombre de tu bucket, y haz clic en **Guardar cambios**.

```json
{
"Version":"2012-10-17",
"Statement":[
  {
    "Sid":"AddPerm",
    "Effect":"Allow",
    "Principal": "*",
    "Action":["s3:GetObject"],
    "Resource":["arn:aws:s3:::your-website/*"]
  }
]
}
```

Verás advertencias sobre hacer público el bucket, pero este paso es necesario para el alojamiento de sitios web estáticos.

Si no estuviéramos aprendiendo sobre el alojamiento estático, el bucket podría ser privado y no haría falta escribir ninguna política. Al configurar la distribución de CloudFront, esta actualizaría automáticamente la política del bucket para acceder al contenido mediante el usuario Origin Access Identity.
