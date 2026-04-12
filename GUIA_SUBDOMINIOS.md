# Guía de Gestión - minera.uno

Este proyecto está configurado para "enmascarar" tus Google Apps Scripts bajo el dominio `minera.uno`.

## 1. Cómo añadir nuevos subdirectorios
Para añadir una nueva ruta (ej. `minera.uno/nueva-pagina`), abre el archivo `vercel.json` y añade estas líneas dentro de la lista `"rewrites"`:

```json
{
  "source": "/nueva-pagina",
  "destination": "https://script.google.com/macros/s/TU_NUEVO_SCRIPT_ID/exec"
},
{
  "source": "/nueva-pagina/:path*",
  "destination": "https://script.google.com/macros/s/TU_NUEVO_SCRIPT_ID/exec/:path*"
}
```

## 2. Cómo vincular tu dominio de GoDaddy
Una vez que despliegues este proyecto en Vercel:
1. Ve a la pestaña **Settings** > **Domains** en tu panel de Vercel.
2. Escribe `minera.uno` y haz clic en **Add**.
3. Vercel te dará unos valores (Tipo A o CNAME).
4. Ve a tu panel de **GoDaddy** > **Administración de DNS**.
5. Cambia los registros DNS por los que te dio Vercel.
6. ¡Listo! En unos minutos `minera.uno/cerro` estará funcionando.

## 3. Notas importantes
- **X-Frame-Options:** Recuerda que cada script de Google que uses DEBE tener la línea `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)` para que no falle el enmascaramiento.
