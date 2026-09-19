# Portafolio — Francisco Javier Elis Cartaya

Sitio estático de una sola página. No necesita compilar nada ni instalar dependencias.

## Contenido

```
index.html      la página completa
support.js      runtime necesario para que la página funcione
assets/         foto y logos de clientes
.nojekyll       evita que GitHub Pages ignore archivos
```

## Subirlo a GitHub

1. Crea un repositorio nuevo en github.com. Nómbralo `portafolio` (o `tuusuario.github.io` si quieres que viva en la raíz de tu dominio de GitHub).
2. En la página del repo vacío pulsa **uploading an existing file**.
3. Arrastra todo el contenido de esta carpeta. Importante: los archivos deben quedar en la raíz del repo, no dentro de una subcarpeta.
4. Escribe un mensaje de commit y pulsa **Commit changes**.

Si prefieres la terminal:

```bash
cd sitio
git init
git add .
git commit -m "Portafolio"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/portafolio.git
git push -u origin main
```

## Publicarlo con GitHub Pages

1. En el repo: **Settings → Pages**.
2. En *Source* elige **Deploy from a branch**.
3. Branch: `main`, carpeta: `/ (root)`. Guarda.
4. En un par de minutos queda en `https://TU-USUARIO.github.io/portafolio/`.

## Dominio propio

Por ahora el sitio vive en `https://franj1748.github.io/portfolio/`. Si más adelante quieres un dominio propio:

1. Compra el dominio donde prefieras.
2. En tu proveedor de DNS crea estos registros:

   | Tipo  | Nombre | Valor |
   |-------|--------|-------|
   | A     | @      | 185.199.108.153 |
   | A     | @      | 185.199.109.153 |
   | A     | @      | 185.199.110.153 |
   | A     | @      | 185.199.111.153 |
   | CNAME | www    | franj1748.github.io |

3. Crea un archivo `CNAME` en la raíz del repo con tu dominio (una sola línea, sin `https://`).
4. En **Settings → Pages → Custom domain** escribe el mismo dominio y marca **Enforce HTTPS**.
5. Actualiza `canonical`, `og:url`, `og:image` y `twitter:image` en `index.html` con el dominio nuevo.

## Formulario de contacto

Funciona con Web3Forms. La Access Key está en `index.html` (`var WEB3FORMS_KEY`). Es pública por diseño: solo sirve para enviar correo a la dirección que verificaste.

Plan gratis: 250 envíos al mes. Si se agota, el sitio muestra un aviso con un botón que abre el cliente de correo del visitante con todos los datos ya cargados, así que nunca se pierde un contacto.

## Editar el contenido

Todo el texto vive en `index.html`, dentro del bloque `var DATA = {`, al final del archivo. Cada campo tiene su versión en español e inglés (`es` / `en`). Cambia el texto entre comillas y sube el archivo otra vez; GitHub Pages republica solo.
