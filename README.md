# IAScorch

**Scorchline: Arena de Artillería** es una adaptación para navegador del clásico **Scorch / Scorched Earth**. Recupera los duelos de tanques por turnos: elegir un arma, ajustar el ángulo y la fuerza del disparo y calcular una trayectoria que alcance al enemigo sobre un terreno destructible.

El juego está desarrollado con **HTML, CSS y JavaScript**, y todo está incluido en un único archivo: [`index.html`](index.html).

## Características

- **Un jugador contra cinco rivales controlados por IA**, en una arena de todos contra todos. Los enemigos también combaten entre sí.
- **Terreno generado aleatoriamente** y posiciones iniciales repartidas al azar en cada partida.
- **Escenario destructible**: las explosiones abren cráteres y pueden dejar a los tanques sin apoyo, provocando caídas y daño adicional.
- **Disparos balísticos** con gravedad, control de ángulo y fuerza.
- **Cinco tipos de armamento**, con munición especial limitada.
- **Botín de combate**: al destruir un rival con tus disparos, puedes recuperar un misil especial de las reservas que le queden.
- **IA que ajusta sus disparos** a partir de los impactos anteriores.
- **Interfaz en español**, con indicadores de integridad, turnos, unidades supervivientes y eventos del combate.
- **Efectos visuales y sonoros** de lanzamiento, explosión, destrucción y fin de partida.
- **Diseño adaptable** con controles en pantalla para ratón y dispositivos táctiles.

## Cómo ejecutar el juego

1. Descarga o clona este repositorio.
2. Abre `index.html` en un navegador moderno con JavaScript habilitado.
3. La partida comienza automáticamente.

No es necesario instalar dependencias, compilar ni iniciar un servidor. El juego es autocontenido y puede ejecutarse sin conexión una vez descargado. Los efectos de sonido se activan al realizar el primer disparo del jugador.

## Cómo jugar

Controlas a **NOVA-01**, que comienza con un 100 % de integridad. Tus rivales son **VANTA, MICA, KERN, ION y RIFT**. El objetivo es ser el último tanque en pie; si NOVA-01 es destruido, la partida termina.

En tu turno:

1. **Selecciona un arma** según la distancia al objetivo, el terreno y la munición disponible.
2. **Ajusta el ángulo**, entre 0° y 180°: 0° apunta a la derecha, 90° hacia arriba y 180° a la izquierda.
3. **Ajusta la fuerza**, entre el 18 % y el 100 %.
4. Pulsa **Disparar** o la barra espaciadora.
5. Observa el impacto y espera a que los rivales completen sus turnos para corregir tu siguiente disparo.

Ten en cuenta tanto el daño de las explosiones como los cambios del terreno. Un cráter puede hacer caer a un tanque, y una explosión cercana también puede dañarte.

## Controles

Puedes utilizar los deslizadores de **Ángulo** y **Fuerza**, los botones de armamento y el botón **Disparar** de la interfaz.

| Tecla | Acción |
| --- | --- |
| `A` o `←` | Aumentar el ángulo de tiro |
| `D` o `→` | Reducir el ángulo de tiro |
| `W` o `↑` | Aumentar la fuerza |
| `S` o `↓` | Reducir la fuerza |
| `1` | Seleccionar misil normal |
| `2` | Seleccionar misil de racimo |
| `3` | Seleccionar misil grande |
| `4` | Seleccionar misil nuclear |
| `5` | Seleccionar misil sísmico |
| `Espacio` | Disparar durante tu turno |
| `R` | Reiniciar la partida con una nueva arena |

Los atajos del juego no se procesan mientras el foco está en un botón o un deslizador; haz clic en la arena para volver a utilizarlos. También puedes empezar de nuevo con **Nueva arena** o con **Reiniciar combate** en la pantalla de resultado.

## Armamento

La munición indicada es la disponible para NOVA-01 al inicio de cada partida.

| Arma | Munición inicial | Efecto |
| --- | --- | --- |
| **Normal** | Ilimitada | Proyectil básico con explosión y cráter de menor tamaño. |
| **Racimo** | 2 | Se divide en cinco proyectiles al comenzar el descenso, si no ha impactado antes. |
| **Grande** | 3 | Mayor daño y radio de explosión que el misil normal. |
| **Nuclear** | 1 | Explosión de gran alcance, alto daño y un cráter de gran tamaño. |
| **Sísmico** | 1 | Excava una franja amplia del terreno, pudiendo provocar caídas. |

Las armas especiales consumen una unidad por disparo. Al agotar el arma especial seleccionada, se vuelve automáticamente al misil normal. El botín puede reponer munición especial durante la partida.

## Tecnologías

- **HTML5** para la estructura de la interfaz.
- **CSS** para el diseño visual y la adaptación a distintos tamaños de pantalla.
- **JavaScript sin frameworks** para las reglas del juego, la física y la IA.
- **Canvas 2D** para dibujar la arena, los tanques, los proyectiles y las partículas.
- **Web Audio API** para generar los sonidos, sin archivos de audio externos.
- **`requestAnimationFrame`** para el bucle de animación.

## Estructura del proyecto

```text
IAScorch/
├── index.html    # Juego completo: interfaz, estilos y lógica
└── README.md     # Descripción y guía de uso
```

Para modificar el juego, edita `index.html` y recarga la página en el navegador. El bloque `<style>` contiene los estilos y el bloque `<script>` incluye la configuración de armas, la generación del terreno, la física, la IA y los controles.
