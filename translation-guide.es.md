# quarkus.io Proyecto de traducción - Guía de traducción

Proyecto de traducción de quarkus.io se está trabajando en la traducción de [quarkus.io](https://quarkus.io).

## Método de traducción

[quarkus.io](https://quarkus.io) es un sitio estático que utiliza Jekyll y su contenido está descrito por asciidoctor (.adoc).
El repositorio se encuentra en [quarkusio/quarkusio.github.io](https://github.com/quarkusio/quarkusio.github.io) y se publica bajo CC BY 3.0.
En este proyecto, usamos una utilidad llamada po4a para extraer el texto de un archivo .adoc, traducirlo, volver a escribirlo en el archivo .adoc y compilarlo para crear un sitio en versión español.
El flujo de trabajo de extracción de texto mediante po4a, la aplicación de texto traducido mediante memoria de traducción, la traducción de borradores mediante traducción automática y el procesamiento de reescritura están automatizados por GitHub Actions en este repositorio.
El texto extraído se almacena en el [directorio l10n](l10n) como un archivo .po, que es un formato de archivo que administra el texto traducido.

## Contribución a la traducción

Si desea contribuir a la traducción, clone este repositorio localmente, edite el archivo .po en [directorio l10n](l10n) y envíe un Pull-Request.
Puede consultar el estado de traducción de cada archivo desde [aquí](l10n/stats/translation.csv).

## Declaración para iniciar la traducción

Al iniciar el trabajo de traducción, para evitar el desperdicio causado por varios miembros que trabajan en el mismo archivo al mismo tiempo y la duplicación del trabajo.
Indique en qué archivo y rango desea comenzar a trabajar en GitHub Issue.
Por el contrario, cuando haga un problema, verifique si alguien ya ha declarado trabajo en el objetivo en el problema existente.

### Trabajo de traducción

El archivo .po es un archivo de texto, pero varias herramientas de ayuda a la traducción admiten la edición. Por ejemplo, [POEdit](https://poedit.net/)
Es compatible con la ejecución en Windows/Mac/Linux y tiene abundantes teclas de atajos, por lo que es cómodo de usar al editar.

### Importación y traducción automáticas de objetivos de traducción

Cuando se actualice [quarkus.io](https://quarkus.io), los archivos que se traducirán se agregarán periódicamente a este repositorio mediante el flujo de trabajo de GitHub Actions.
Se importará automáticamente y se creará un archivo .po. El archivo .po contiene traducciones existentes almacenadas en la memoria de traducción y
Usando [quarkus-adoc-po-translator](https://github.com/doc-l10n-kit/quarkus-adoc-po-translator)
Se insertará el texto traducido automáticamente por la API de DeepL, así que utilícelo como una traducción aproximada al traducir.

Sin embargo, dado que es una traducción automática hasta el final, hay muchas partes no naturales como teniwoha, y está marcado como "confirmación requerida" (borroso), y no se reflejará como una traducción a menos que la marca "confirmación requerida" se elimina...
Revise y corrija la traducción y elimine la marca de "confirmación requerida".

### Archivo traducido

En el futuro me gustaría traducir todos los archivos .po del [directorio l10n](l10n), pero antes que nada, traducir el contenido principal "guías" [directorio l10n/po/es_ES/_guides](l10n/po/es_ES/_guides).
Para continuar, me gustaría traducir el "blog" en [directorio l10n/po/es_ES/_posts](l10n/po/es_ES/_posts).

### Manejo de oraciones sin traducción

El archivo .po puede contener oraciones que no necesitan ser traducidas en su totalidad, como el código fuente y las URL.
En ese caso, no hay necesidad de copiar el texto original tal como está. Por favor, deje la traducción en blanco. Entonces se utilizará el texto original tal como está.

### Vista previa de los resultados de la traducción

Si traduce el archivo .po y obtiene un Pull-Request, el sitio se construirá automáticamente con GitHub Actions, y la URL donde puede visitar el sitio temporalmente será enviada como un comentario en el Pull-Request en GitHub en aproximadamente 5 minutos.
Puede revisar la vista previa del resultado de la traducción en ese sitio temporal, así que por favor utilícelo.

### Soporte/traducción de actualización de plantillas HTML

El contenido de quarkus.io está escrito en asciidoctor (.adoc), pero parte del texto está incluido en la plantilla HTML de Jekyll.
El texto escrito en la plantilla HTML de Jekyll no se puede programar en po4a, así que póngalo en el [directorio l10n/override](l10n/override).
Coloque una copia de los archivos que po4a no puede manejar, traduzca este archivo manualmente y utilícelos cuando construya el sitio de Jekyll.
La localización se logra sobrescribiendo el archivo original.
Si el archivo original se actualiza en upstream, también es necesario actualizar el archivo copiado en [l10n/override directory](l10n/override).
Tenga en cuenta que, en este momento, no existe ninguna función para detectar y notificar la actualización del archivo original en upstream.
