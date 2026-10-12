# Registro de Matrícula 2027 — Escuela Barrio Los Ángeles

Página lista para publicar en **GitHub Pages** (gratis y con enlace permanente).

| Archivo | Descripción |
|---|---|
| `index.html` | La página completa. **GitHub Pages exige este nombre** exacto. |
| `encabezado.png` | Encabezado institucional que muestra la página (suba este archivo junto con el HTML). |
| `.nojekyll` | Archivo vacío que le indica a GitHub que sirva los archivos tal cual, sin procesarlos con Jekyll. |
| `README.md` | Este archivo (solo se muestra en GitHub; la página no lo usa). |

---

## ⚠️ PASO 0 (muy importante): pegue la URL de Google Apps Script en `index.html`

Si la URL queda vacía, **cada familia que abra la página quedará en «modo local» y la escuela
NO recibirá sus boletas**. Antes de subir el archivo:

1. Abra `index.html` con el Bloc de notas o con VS Code.
2. Busque esta línea (aprox. línea 1324, dentro de `var CONFIG = {`):

   ```js
   urlAppsScript: "",
   ```

3. Reemplácela por la URL de **su app web publicada** (la que termina en `/exec`), entre comillas:

   ```js
   urlAppsScript: "https://script.google.com/macros/s/AKfyc.../exec",
   ```

   (La línea debe conservar exactamente el nombre `urlAppsScript` con la S mayúscula.)

   ¿No la tiene? Créela una sola vez: hoja de cálculo en Google Drive ▸ Extensiones ▸ Apps Script ▸
   pegue el código de `Codigo Apps Script - Registro Matricula 2027.gs` ▸ ejecute **INSTALAR** ▸
   Implementar ▸ Nueva implementación ▸ App web ▸ copie la URL `/exec`.
   En la propia página también está la guía: **Ayuda** ▸ *Publicación en línea* y
   **Área administrativa** ▸ *Instalación asistida* (allí puede verificarla y copiar la línea lista).

4. Guarde el archivo.

### URL guardada (se actualiza automáticamente)

<!--URL-APPS-SCRIPT-INICIO-->
**URL guardada actualmente:** `https://script.google.com/macros/s/AKfycbxzEqQMtmgsQ7k_lDtc8nnmo2rxCQcDJMp6e4Fq2EBy0MrtctNkO3kQ0v7Xe4f_LKLkyA/exec`

```js
urlAppsScript: "https://script.google.com/macros/s/AKfycbxzEqQMtmgsQ7k_lDtc8nnmo2rxCQcDJMp6e4Fq2EBy0MrtctNkO3kQ0v7Xe4f_LKLkyA/exec",
```
<!--URL-APPS-SCRIPT-FIN-->

> **Actualización automática del Paso 0:** entre al **Área administrativa ▸ Instalación asistida**,
> seleccione la **carpeta de publicación** (esta misma carpeta) y pulse **Verificar y guardar**:
> este Paso 0 y la línea `urlAppsScript` del `index.html` de la carpeta se actualizan solos con la
> URL guardada. Luego solo suba los archivos a GitHub (botón **Actualizar README e index.html**
> permite repetirlo manualmente).

> La contraseña del panel administrativo por defecto es `MAT2027`
> (`CONFIG.claveAdmin`). Cámbiela desde **Área administrativa ▸ Administradores** antes de publicar.

---

## Publicar (4 pasos)

1. **Cuenta**: crea una cuenta gratuita en <https://github.com> (si ya tiene una, inicie sesión).

2. **Repositorio**: botón **+** (arriba a la derecha) ▸ **New repository**:
   - *Repository name*: un nombre en minúsculas sin espacios, ej. `matricula-2027`.
   - Seleccione **Public** (debe ser público para Pages gratuito).
   - **No** marque "Add a README file" (si lo marcó, borre ese README antes de subir estos archivos).

3. **Subir archivos**: dentro del repositorio ▸ botón **Add file** ▸ **Upload files** ▸
   arrastre `index.html`, `encabezado.png`, `.nojekyll` y `README.md` ▸ **Commit changes**.

4. **Activar Pages**: **Settings** ▸ menú lateral **Pages** ▸ en *Build and deployment*:
   - *Source*: **Deploy from a branch**
   - *Branch*: **main** / carpeta **/(root)** ▸ **Save**

En 1–2 minutos tendrá su enlace permanente:

```
https://TUUSUARIO.github.io/matricula-2027/
```

(Formato general: `https://TUUSUARIO.github.io/NOMBREDELREPOSITORIO/`.)

---

## Cómo actualizar la página después

Cada vez que modifique la boleta o cualquier texto:

- **Opción A (web)**: abra `index.html` en el repositorio ▸ botón **✎ (Edit)** ▸ pegue el contenido
  nuevo del archivo local ▸ **Commit changes**. En ~1 minuto queda publicado.
- **Opción B (web)**: elimine el `index.html` viejo (papelera ▸ Commit) y vuelva a subirlo con
  **Add file ▸ Upload files**.
- **Opción C (git)**, desde la carpeta "Publicar en GitHub Pages":

  ```bash
  git init
  git add .
  git commit -m "Actualiza página de matrícula"
  git branch -M main
  git remote add origin https://github.com/TUUSUARIO/matricula-2027.git
  git push -u origin main
  ```

---

## Qué funciona en línea y qué no

- **Boletas de las familias** (cualquier navegador/celular): funcionan **en línea** siempre que la
  URL `/exec` esté pegada en `index.html`. Los registros caen en la hoja **MATRICULA2027** de Google
  y la escuela recibe el correo de notificación por Google según su CONFIG.
- **Puente local (Excel en una ruta + Outlook)**: solo corre en la PC de la escuela donde se ejecuta
  `Iniciar puente matricula.bat` (127.0.0.1). Al abrir la página publicada en **Chrome o Edge** en
  esa PC, con el token configurado en *Área administrativa ▸ Excel y Outlook*, los envíos hechos
  allí se guardan también en su Excel y se avisa por Outlook. Si el puente no responde, la página
  sigue el camino normal (Google o modo local).
- **Carpeta Excel (guardado automático en la PC del administrador)**: desde la página publicada, el
  administrador entra al panel y pulsa **Carpeta Excel ▸ Seleccionar carpeta…** (Chrome/Edge) para
  elegir una carpeta de **su equipo**; allí se crea y se reescribe solo el archivo
  `MATRICULA_2027.xlsx` con el mismo formato de la exportación (50 columnas + hoja INFORMACIÓN)
  cada vez que hay una matrícula nueva o cambia un estado. Cada equipo elige su propia carpeta y
  el navegador recuerda el permiso (si lo vuelve a pedir, basta concederlo de nuevo).
- **Panel administrativo**: los registros "En línea" se ven con el botón *Refrescar* en cualquier
  equipo; los registros capturados en modo local quedan en el navegador donde se hicieron
  (exporte respaldos .json desde el panel).

---

Desarrollado por el **Ing. Jonathan Díaz Ramírez** · Registro de Matrícula 2027 ·
Escuela Barrio Los Ángeles (Código 1389).
