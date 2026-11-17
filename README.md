# Transferencia de cantidad de movimiento

Calculadora web para resolver problemas de transferencia de cantidad de movimiento, con los pasos de la solución, una gráfica y el porcentaje de error contra un dato experimental.

**Úsala en línea:** https://sebastian-gal.github.io/transferencia-movimiento/

Funciona en cualquier navegador, también en celulares Android, sin instalar nada ni crear cuenta.

## Problemas que resuelve

1. **Viscosidad de un gas a baja densidad (Chapman-Enskog).** Ecuaciones 11.1 a 11.3 y tabla 11.1 del compendio de fenómenos de transporte.
   - Sustancias de la tabla 11.1 precargadas (M, σ, ε/k).
   - Tres formas de calcular la integral de colisión Ωμ: la ecuación 11.3 con 4.º término (como en el examen), la de 3 términos y la de Neufeld completa. También se puede capturar Ωμ a mano.
   - Avisa si T* queda fuera del rango válido (0.3 a 100).
2. **Esfuerzo cortante en una tubería.** Balance de cantidad de movimiento en un tubo circular: τrz = −Pg·r/2 y esfuerzo en la pared |τw| = Pg·R/2.

Los dos aceptan varias unidades (°C/K, μP/P/cP/Pa·s, m/cm/mm, Pa/kPa, Pa/m/kPa/m) y calculan el % de error si se captura el valor experimental.

## Usarla sin internet

Todo el programa vive en un solo archivo, `index.html`:

1. Descarga [`index.html`](index.html) (botón *Download raw file*).
2. En Android, ábrelo desde la app **Archivos** y elige **Chrome**.

Sin internet funciona igual; solo cambia la tipografía.

## Código

- `index.html`: interfaz, estilos y lógica en HTML, CSS y JavaScript, sin librerías externas.
- La parte de cálculo está entre los comentarios `/*CORE-START*/` y `/*CORE-END*/`. Es una traducción directa del programa de escritorio en Python (paquete `transporte`); se comprobó con 17 casos que da exactamente los mismos resultados, pasos y mensajes de error.

### Agregar un problema nuevo

Crea un objeto con `id`, `title`, `subtitle`, `fields`, `example()` y `compute(v)`, siguiendo el modelo de `chapman` o `tuberia`, y agrégalo a la lista `PROBLEMS`. El formulario, las pestañas, los resultados y la gráfica se generan solos a partir de esos datos.
