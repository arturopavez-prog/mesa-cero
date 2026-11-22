# Validación funcional que Claude debe completar

- [ ] `https://.../mesa-cero/` abre sin error 404.
- [ ] El tablero muestra **4 misiones**, **12 clases**, **4 prácticas**, **4 exámenes** y **4 casos**.
- [ ] Clase 1: ofrece lectura + ejemplo + pregunta de comprensión. No permite hacer examen inmediatamente.
- [ ] Responder correctamente la pregunta de la clase 1 la marca como comprendida y deja avanzar.
- [ ] Tres clases completadas habilitan una práctica guiada sin nota.
- [ ] Tras la práctica: un examen de 5 preguntas con límite real de 8 minutos y mínimo de 80%.
- [ ] Antes de aprobar, el caso escrito permanece bloqueado.
- [ ] Tras aprobar, el caso permite guardar argumentos, muestra pauta comparativa y no finge corrección con IA.
- [ ] El progreso persiste después de refrescar o cerrar la pestaña.
- [ ] Botones **Guardar respaldo JSON**, **Restaurar JSON** y **Descargar bitácora TXT** funcionan.
- [ ] La app tiene un archivo `manifest.webmanifest` válido, íconos 192/512 y `sw.js` activo.
- [ ] Desde Android Chrome se ofrece instalación o alternativa en el menú `⋮`.
- [ ] Tras visitar el sitio una vez con conexión y dejarlo almacenar en caché, puede abrirse sin conexión.
- [ ] El repo y despliegue de Spinning siguen intactos.

No declarar un punto aprobado sin comprobarlo. Las pruebas de Android real se hacen en dispositivo, no sólo en navegador de escritorio.

## Entrenador de constancia (2.2)

- [ ] Menú «Constancia» abre la sección con racha, semana y minutos de hoy.
- [ ] Responder una clase suma un día activo y la racha.
- [ ] Repaso relámpago no cambia el avance del curso.
- [ ] Cambiar días del plan actualiza la meta semanal.
- [ ] «Descargar recordatorio» abre en el Calendario de Android con alarma.
