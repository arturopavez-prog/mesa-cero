# MESA CERO 2.2 — Entrenador de constancia

Fecha: 2026-11-21. Base: MESA CERO 2.1 (contenido, motor y reglas sin cambios).

## Qué se agregó
- **Sección «Constancia»** (menú lateral 🔥) y tarjeta resumen en el Tablero.
- **Racha diaria**, mejor racha, semanas cumplidas seguidas y días activos totales.
- **Plan semanal**: eliges tus días de estudio (meta semanal = nº de días), minutos por sesión (10/15/20/30) y hora.
- **Plan si-entonces** («Cuando…, abriré MESA CERO»).
- **Mapa de 4 semanas**: días activos y días planificados sin sesión (sólo desde que empezaste a usar la app).
- **Micro-paso siguiente**: botón directo a la próxima clase/práctica/examen/caso, respetando el orden enseñar → practicar → evaluar.
- **Repaso relámpago**: repite la pregunta de comprensión de una clase ya aprobada (la que llevas más tiempo sin ver). **Sin nota y sin efecto en el avance.**
- **Regla de oro**: aviso si ayer era día planificado y no hubo sesión («nunca faltar dos días seguidos»).
- **Recordatorio para Calendario (.ics)**: evento semanal con alarma en tus días y hora. La app no envía notificaciones con la app cerrada porque eso exigiría un servidor.
- **Tiempo activo**: suma minutos sólo con la app visible y con interacción en los últimos 2 minutos.

## Qué cuenta como día activo
Responder una clase, avanzar la práctica, responder el examen, entregar el caso, un repaso relámpago, completar los minutos de la meta o «Marcar sesión de hoy».

## Datos
- Se guarda dentro del mismo progreso local (`mesa_cero_personal_v2`, campo `habit`). Se mantiene `v:2`: el progreso anterior no se pierde.
- El respaldo JSON y la bitácora TXT incluyen la constancia. Restaurar JSON la conserva.
- `sw.js`: caché renombrada a `mesa-cero-static-v2.2.0` para forzar actualización.

## Correcciones
- Ajuste por la nueva vista: el ítem «Tablero» del menú se marcaba activo con cualquier índice de vista negativo; ahora sólo en el Tablero.
- En la 2.1 original no se encontraron errores: sin errores de consola; bancos de preguntas válidos (índices correctos y 5 preguntas distintas en 8 intentos por misión).

## Pruebas automáticas realizadas (Chrome headless, viewport Android 412×915)
Tablero con 4 misiones/12 clases/Continuar · clase 1 no avanza con respuesta incorrecta y sí con la correcta · examen bloqueado antes de la práctica · progreso persiste al recargar · respaldo JSON y bitácora TXT descargan · racha y semana calculan bien con historial simulado · repaso no altera avance · .ics semanal con alarma · service worker activo · recarga sin conexión muestra la academia · manifest standalone con 2 íconos.

## Corrección de publicación (repo mesa-cero)
- `deploy.yml`: se agregó `enablement: true` a `actions/configure-pages` para intentar activar GitHub Pages automáticamente si aún no está activado.
