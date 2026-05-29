[README.md](https://github.com/user-attachments/files/28371583/README.md)
# 📦 Panel HD Valdishopper – Guía de GitHub

Cómo dejar el dashboard **100% automático**: subes el Excel → recargas la página → todo se actualiza solo.

---

## 🚀 Paso 1 – Crear el repositorio en GitHub

1. Ve a [github.com](https://github.com) e inicia sesión (o crea una cuenta gratis).
2. Haz clic en **"New repository"** (botón verde arriba a la derecha).
3. Nómbralo, por ejemplo: `panel-hd`
4. Márcalo como **Public** ✅ (necesario para que el HTML pueda leer el Excel sin token).
5. Haz clic en **"Create repository"**.

---

## 📁 Paso 2 – Subir los archivos

Arrastra y suelta (o usa "Add file → Upload files") los dos archivos al repo:

| Archivo | Descripción |
|---|---|
| `Panel_HD_v3.html` | El dashboard |
| `Planificacion_HD.xlsx` | El Excel con todos los datos |

> ⚠️ El nombre del Excel debe ser **exactamente** el mismo que pusiste en la config del HTML.

---

## ⚙️ Paso 3 – Configurar el HTML (solo una vez)

Abre `Panel_HD_v3.html` en un editor de texto (Notepad, VS Code, etc.) y busca esta sección cerca del principio del `<script>`:

```javascript
// 👇 EDITA ESTAS 3 LÍNEAS con tus datos de GitHub
const GITHUB_USER   = 'TU_USUARIO';           // ej: 'valdishopper'
const GITHUB_REPO   = 'TU_REPOSITORIO';       // ej: 'panel-hd'
const EXCEL_PATH    = 'Planificacion_HD.xlsx'; // nombre exacto del archivo
```

Reemplaza los valores:

```javascript
const GITHUB_USER   = 'valdishopper';         // tu usuario real de GitHub
const GITHUB_REPO   = 'panel-hd';             // nombre del repo que creaste
const EXCEL_PATH    = 'Planificacion_HD.xlsx'; // nombre del Excel en el repo
```

Guarda el archivo y **vuelve a subirlo** al repo (sobreescribe el anterior).

---

## 🌐 Paso 4 – Activar GitHub Pages (para abrirlo como web)

1. En tu repo, ve a **Settings → Pages** (menú lateral izquierdo).
2. En "Source" selecciona **"Deploy from a branch"**.
3. Elige la rama **`main`** y carpeta **`/ (root)`**.
4. Haz clic en **Save**.
5. Espera ~1 minuto y aparecerá una URL del tipo:
   ```
   https://TU_USUARIO.github.io/panel-hd/Panel_HD_v3.html
   ```

¡Esa es tu URL permanente! Compártela con tu equipo.

---

## 🔄 Paso 5 – Actualizar datos (uso diario)

Cada vez que quieras actualizar el dashboard:

1. Guarda los cambios en tu Excel (`Planificacion_HD.xlsx`).
2. Entra al repo en GitHub.
3. Haz clic en el archivo Excel → **"Replace this file"** (o arrastra el nuevo).
4. Escribe un mensaje de commit como `"Actualización semana 22"` y confirma.
5. **Recarga la página** del dashboard → los datos se actualizan automáticamente.

> El dashboard siempre lee la versión más reciente del Excel al cargar.

---

## 📋 Hojas del Excel que usa el dashboard

| Hoja | Pestaña del dashboard |
|---|---|
| `Flota actual VS` | 🚛 Flota HD Valdishopper |
| `Mapeo de flota` | 🚐 Estado Flota FH |
| `Check FLE` | ⚡ Check FLE |
| `Hoja 27` | 🎓 Inducciones |
| `Revision RS` | 📋 Revisión RS |
| `CItaciones FH` | 📅 Citaciones FH |
| `Copia de CItaciones FLD ` | 🗓️ Citaciones FLD/MM |
| `Post Estival` | 🔄 Rotación Citaciones HD |

> ⚠️ No cambies el nombre de las hojas del Excel, el dashboard las busca por nombre exacto.

---

## ❓ Problemas frecuentes

| Problema | Solución |
|---|---|
| "Error: HTTP 404" | El Excel no está en el repo o el nombre está mal escrito |
| Sale "Modo demo" | No editaste `GITHUB_USER` / `GITHUB_REPO` en el HTML |
| Datos vacíos en alguna pestaña | El nombre de la hoja Excel cambió |
| Repo privado no funciona | Cámbialo a **Public** en Settings → General |

---

_Valdishopper · Panel HD · Generado automáticamente_
