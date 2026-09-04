# Este sitio se apagó el 04-09-2026

Acá vivía la página de venta de Quantika. **Ya no.** El sitio del producto es:

## → https://quantikaviewer.com

---

## Por qué se apagó

Vendía el plugin a **US$26 / US$260** con cinco botones de MercadoPago vivos, cuando el precio real
pasó a **$45.000 / $405.000 CLP**. O sea: cobraba la mitad, y el botón funcionaba. Cualquiera que la
encontrara en Google pagaba de menos.

## Por qué no se pudo apagar antes

Por una razón que no tenía nada que ver con el precio: **el botón «Descargar» del sitio nuevo bajaba
el instalador desde acá**, y la página de allá además leía este `version.json` para mostrar la versión.
Borrar esto dejaba la descarga del sitio **nuevo** apuntando a la nada.

Eso se resolvió el 03-09: el instalador se mudó al almacenamiento de Cloudflare y se sirve por
`https://quantikaviewer.com/descargar/Quantika-Setup-vN.N.N.exe`, con su propio manifiesto en
`https://quantikaviewer.com/version.json`. Recién entonces esto quedó libre.

## Lo único que quedó

**`version.json`**, y a propósito. Su dirección está **compilada adentro de cada Quantika ya
instalado**: un plugin instalado consulta la dirección con la que se compiló y ninguna otra. Si esto
dejara de responder, esas instalaciones no se enterarían nunca más de una versión nueva — y no hay
otro canal para avisarles, porque el aviso ES este archivo.

Así que en vez de borrarlo, **reenvía**: dice la versión de verdad y apunta al instalador del sitio
nuevo. Pesa dos kilobytes y hace que el canal de actualización siga funcionando.

Se podrá borrar del todo cuando salga una versión del plugin que apunte al manifiesto nuevo y el
parque instalado la haya tomado. Nunca al revés. (Está explicado, con su guardián, en
`Prueba2/Services/UpdateService.cs`.)

## Y lo que estaba acá

Los instaladores viejos (1.7.1, 1.7.2, 1.7.3), los `.zip` de las 1.0.x, las capturas y las páginas
**siguen en el historial de git**. No se perdió nada: `git log` y `git show` los tienen.
