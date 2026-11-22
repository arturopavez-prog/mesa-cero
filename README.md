# MESA CERO 2.2 — Academia personal de negociación bajo presión

> **Primero enseñar. Después practicar sin nota. Finalmente evaluar.**

Este repositorio contiene una **Progressive Web App (PWA)** estática, en español de Chile, lista para publicar en GitHub Pages e instalar en un teléfono Android como una app con ícono propio. No necesita servidor, base de datos, cuentas, contraseñas, API ni servicios pagos.

## Contenido académico ya incluido

- 4 misiones secuenciales de aprendizaje.
- 12 clases (3 por misión), cada una con explicación, ejemplo resuelto y pregunta de comprensión.
- 4 prácticas guiadas **sin nota**.
- 4 evaluaciones objetivas contrarreloj: 5 preguntas, 8 minutos, aprobación **≥80 %**.
- 4 casos escritos con pauta para revisión crítica posterior. La app **no afirma corregir automáticamente** la calidad del razonamiento abierto.
- Tablero con porcentaje de avance y desbloqueo por requisitos.
- Bitácora descargable `.txt` y respaldo/restauración `.json`.
- **Entrenador de constancia (2.2)**: racha, plan semanal, micro-paso, repaso relámpago sin nota y recordatorio para Calendario. Ver `CAMBIOS_2_2.md`.

La edición 2.1 conserva el motor y el contenido de MESA CERO 2.0 y agrega manifest, íconos, service worker y guía de instalación. **La clave de almacenamiento `mesa_cero_personal_v2` se mantiene para no borrar el progreso de la versión anterior cuando se usa en el mismo origen del navegador.**

## Publicación en GitHub Pages (recomendado)

1. Crear un repositorio **nuevo e independiente** llamado `mesa-cero` en la cuenta GitHub deseada. **No subir esto al repositorio de Spinning ni reemplazar archivos de Spinning.**
2. Subir **el contenido de esta carpeta a la raíz** del repositorio, incluyendo `index.html`, `sw.js`, `manifest.webmanifest`, `assets/`, `.github/workflows/deploy.yml` y `.nojekyll`. No subir solamente el `.zip`.
3. Usar la rama `main`.
4. En GitHub entrar a **Settings → Pages → Build and deployment → Source: GitHub Actions**.
5. En **Actions** comprobar que la acción “Publicar MESA CERO en GitHub Pages” termine correctamente. Si es necesario, seleccionar **Run workflow**.
6. Abrir la dirección publicada, normalmente `https://USUARIO.github.io/mesa-cero/` (reemplazar USUARIO por el propietario real). No anticipar una dirección sin haberla comprobado.
7. Desde Chrome en Android abrir la dirección HTTPS y tocar **Instalar en celular**. Si no aparece el diálogo nativo, abrir el menú `⋮` → **Instalar aplicación** o **Agregar a la pantalla principal**.

La instalación PWA requiere **HTTPS** o, para pruebas, **localhost**. Abrir `index.html` directamente desde un archivo descargado permite ver contenido, pero no habilita la instalación ni el funcionamiento offline del service worker.

## Prueba local

En una computadora con Python 3, situarse en esta carpeta y ejecutar:

```bash
python -m http.server 8000
```

Abrir `http://localhost:8000` y verificar la app. La instalación real en Android debe probarse después en GitHub Pages.

## Privacidad y respaldo

- La aplicación **no envía** respuestas, progreso ni bitácora a ningún servidor: se guardan en `localStorage` del navegador/origen desde el que se abrió.
- No sincroniza progreso entre dispositivos. El instalador y Chrome pueden usar el mismo almacenamiento según el navegador; **no depender de ello** para migraciones.
- Antes de cambiar de teléfono, navegador, ruta del sitio o borrar sus datos: **Guardar respaldo JSON**. Luego importar ese archivo en la nueva instalación.
- GitHub Pages publica archivos estáticos. Si el repositorio o Pages es público, **el código y el material del curso serán accesibles**, pero **las respuestas locales no se suben**.
- La app es educativa. Ejemplos y casos son ficticios y no constituyen formación operativa de negociación con rehenes.
- Sin red después de la primera carga completa: la app base queda disponible en caché. Enlaces bibliográficos externos requieren conexión.

## Estructura

```text
mesa-cero/
├── index.html                      # Curso completo y lógica
├── manifest.webmanifest            # Instalación como PWA
├── sw.js                           # Uso sin conexión
├── assets/
│   ├── icon.svg
│   ├── icon-192.png
│   └── icon-512.png
├── .github/workflows/deploy.yml    # Despliegue GitHub Pages
├── .nojekyll
├── .gitignore
├── historial/                      # Respaldos sin modificar, no son entrada de la app
│   ├── mesa_cero_1_0_original.html
│   └── mesa_cero_2_0_original.html
├── README.md
├── CLAUDE_INSTRUCCIONES.txt
├── GUIA_INSTALACION_ANDROID.md
└── CHECKLIST_PRUEBAS.md
```

## Actualizaciones futuras

Si modifican recursos esenciales, cambien la cadena `CACHE` en `sw.js` para forzar el recambio de archivos cacheados. Mantener `KEY` de progreso mientras el modelo de datos `v:2` no cambie. No borrar versiones anteriores del curso sin hacer respaldo.
