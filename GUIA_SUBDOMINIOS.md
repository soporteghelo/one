# Guía de Gestión - minera.uno (Método Estable)

Para solucionar los problemas de "pantalla en blanco" de Google, hemos cambiado a un método de **Carpetas Físicas + Iframes**.

## 1. Cómo añadir nuevos subdirectorios (Ej: /capacitacion)
Ya no necesitas editar código JSON. Ahora es mucho más visual:

1. Crea una **nueva carpeta** dentro de `ONE` con el nombre que quieras (ej: `capacitacion`).
2. Copia el archivo `index.html` que está en la carpeta `cerro`.
3. Pégalo dentro de tu nueva carpeta (`capacitacion`).
4. Abre ese nuevo `index.html` y cambia la URL del `src` del iframe por la URL de tu nuevo script de Google.

```html
<iframe src="TU_NUEVA_URL_AQUI" ...></iframe>
```

## 2. Ventajas de este método
- **Estabilidad:** Es casi imposible que Google bloquee este método.
- **Rendimiento:** Vercel sirve los archivos estáticos instantáneamente.
- **Limpieza:** Al entrar a `minera.uno/cerro`, el navegador carga la carpeta físicamente y muestra tu portal.

## 3. Nota sobre GoDaddy
No necesitas cambiar nada en GoDaddy. Si ya pusiste los registros DNS anteriores, seguirán funcionando perfectamente para este nuevo método. Solo vuelve a subir estos cambios a GitHub y Vercel se actualizará solo.
