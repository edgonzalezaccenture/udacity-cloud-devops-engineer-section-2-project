# Subir archivos a S3 Bucket

1. Con el bucket abierto, haz clic en **Cargar**.
2. Con **Agregar archivos** carga `index.html`, y con **Agregar carpeta** carga las carpetas `css`, `img` y `vendor`.

No selecciones la carpeta `udacity-starter-website`: carga su contenido uno por uno. Tampoco cargues el zip de nivel superior ni una carpeta principal, porque crearía un nivel de anidamiento adicional.

La carga puede tardar mucho por la cantidad de archivos. Si es tu caso, mira el problema 2.

## Problema 1: cortafuegos o bloqueador de anuncios

La configuración de red, el cortafuegos o el bloqueador de anuncios del navegador pueden impedir la carga de algún archivo, como `buysellads.svg`.

### Solución 1: desactivar el bloqueador en Chrome

1. Arriba a la derecha, haz clic en Más (tres puntos) > **Settings**.
2. Haz clic en **Security and Privacy** > **Site Settings**.
3. Haz clic en **Additional content settings** > **Ads**.
4. Desactiva **Block ads on sites that show intrusive or misleading ads**.

### Solución 2: cargar con la CLI de AWS

Comprueba la configuración de la CLI. Si aún no está configurada, usa:

```bash
aws configure list
aws configure
aws configure set aws_session_token "<TOKEN>" --profile default
```

Sube los archivos:

```bash
# Crea un bucket PÚBLICO en S3 y compruébalo desde local
aws s3api list-buckets

# Descarga y descomprime udacity-starter-website.zip
cd udacity-starter-website

# Suponiendo que el bucket se llama my-bucket-202203081 y que estás en la carpeta udacity-starter-website
# Sube un solo archivo
aws s3api put-object --bucket my-bucket-202203081 --key index.html --body index.html

# Copia las carpetas de local a S3
aws s3 cp vendor/ s3://my-bucket-202203081/vendor/ --recursive
aws s3 cp css/ s3://my-bucket-202203081/css/ --recursive
aws s3 cp img/ s3://my-bucket-202203081/img/ --recursive
```

## Problema 2: demasiados archivos

Según la velocidad de tu conexión, cargar los archivos directamente puede tardar demasiado. La alternativa es subir el zip y descomprimirlo en el bucket con CloudShell (el curso lo muestra en un vídeo):

```bash
# Copia el zip del bucket a un directorio temporal de CloudShell
aws s3 cp s3://[bucket-path]/udacity-starter-website.zip /tmp/site.zip

# Descomprime el zip temporal en un directorio de CloudShell
unzip /tmp/site.zip -d /tmp/site/

# Carga los archivos y directorios extraídos al bucket
aws s3 cp /tmp/site/ s3://[bucket-path]/ --recursive
```
