# Cuéntame de ti ✨

Formulario interactivo, tipo "web app", pensado para conocer a alguien de forma casual (sin que se sienta como una entrevista de trabajo). Combina preguntas de opción múltiple, chips seleccionables y campos abiertos cortos, con subida de CV **opcional**. Está optimizado para celular y animado con emojis temáticos de e-commerce, marketing, tecnología/IA y belleza.

Las respuestas se envían directo a tu correo (`julioaosorio11@gmail.com`) usando [Web3Forms](https://web3forms.com), un servicio gratuito que no requiere backend ni servidor propio.

## 1. Configura el envío de correo (una sola vez)

1. Entra a https://web3forms.com y crea una cuenta gratis con `julioaosorio11@gmail.com`.
2. Copia el **Access Key** que te generan.
3. Abre `index.html`, busca esta línea cerca del final del archivo:
   ```js
   var WEB3FORMS_ACCESS_KEY = "PON_AQUI_TU_ACCESS_KEY_DE_WEB3FORMS";
   ```
4. Reemplaza el texto entre comillas por tu Access Key real y guarda.

Con eso, cada vez que alguien complete el formulario, vas a recibir un correo con todas sus respuestas (y el CV adjunto, si lo subió).

> Nota: el plan gratuito de Web3Forms soporta archivos adjuntos de hasta unos pocos MB. Si necesitas más volumen o quieres tu propio dominio de envío, pueden pasar a un plan pago sin cambiar nada del formulario.

## 2. Pruébalo localmente

Solo abre `index.html` en el navegador de tu celular o computadora. No necesita instalación ni build.

## 3. Publícalo en un dominio

Cualquiera de estas opciones funciona porque es un solo archivo HTML estático:

### Opción A: Netlify (más fácil, gratis)
1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta del proyecto (o solo `index.html`).
3. Netlify te da una URL al instante (puedes conectar tu propio dominio después en "Domain settings").

### Opción B: Vercel
1. Ve a https://vercel.com/new
2. Importa este repositorio.
3. Deploy con configuración por defecto (no necesita build command).

### Opción C: GitHub Pages
1. En la configuración del repo, activa GitHub Pages apuntando a la rama principal.
2. Tu sitio queda disponible en `https://<usuario>.github.io/<repo>/`.

En cualquiera de los tres, luego puedes conectar un dominio propio desde el panel del proveedor.

## Estructura

- `index.html` — todo el formulario (HTML + CSS + JS en un solo archivo, sin dependencias externas ni build).

## Personalizar preguntas

Cada pregunta es una `<div class="card" data-step="N">` dentro de `index.html`. Puedes agregar, quitar o reordenar tarjetas; el script detecta automáticamente el total de pasos y ajusta la barra de progreso.
