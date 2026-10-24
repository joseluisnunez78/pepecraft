# PepeCraft

Un juego de realidad virtual que se abre en el navegador de las gafas Meta Quest 3, sin instalar nada. Pepe explora un mundo de bloques, cava el terreno con un martillo, se defiende de los zombis con una espada y tiene que recoger 5 monedas lo antes posible. También se puede jugar en el ordenador con teclado y ratón.

Inspirado en Minecraft (solo la idea general de un mundo de bloques; no contiene código, gráficos, sonidos ni nombres de ese juego). No es un juego oficial; mira [LEGAL.md](LEGAL.md).

## Qué tiene

- Un mundo de 64 × 64 columnas de bloques (hierba, tierra, piedra y agua) con texturas pixeladas dibujadas por el propio código. Cada partida perdida empieza en un paisaje nuevo.
- Vacas y ovejas que pasean. Si les das con la espada, se enfadan y salen corriendo (no se les puede hacer daño).
- 5 vidas, 5 monedas que recoger y zombis que te persiguen. Con 2 golpes un zombi muere, pero aparecen dos más aterradores y todos van un poco más rápido.
- Con 3 monedas se desbloquea la **bola de fuego**, que mata a un zombi de un impacto.
- Una **copa dorada** escondida en cada partida: al cogerla saltas el doble de alto durante 20 segundos.
- Con muchos zombis aparece un **dragón** que marca un círculo rojo en el suelo y lanza una llamarada: apártate a tiempo.
- Marcador siempre visible, récord de tiempo guardado, música que se vuelve más frenética y efectos de sonido, todo generado por el código (sin archivos de audio).

## Cómo jugar

El objetivo es recoger las 5 monedas antes de quedarte sin vidas. Cuanto antes, mejor récord.

### En las Meta Quest 3

1. Abre la dirección del juego (la de Vercel, con `https://`) en el navegador de las gafas.
2. Pulsa **Entrar en realidad virtual**.

| Control | Qué hace |
| --- | --- |
| Joystick izquierdo | Andar |
| Joystick derecho | Girar (a saltos de 30°) |
| Botón **A** | Saltar; otra vez en el aire, doble salto |
| Botón **B** | Cambiar entre martillo y espada |
| Golpe rápido con el mando derecho | Usar la herramienta: el martillo cava bloques y daña zombis; la espada daña zombis (y enfada a los animales) |
| Gatillo (cualquier mando) | Lanzar la bola de fuego hacia donde apuntas (con 3 monedas o más) |
| **A** o gatillo derecho en el panel final | Volver a jugar |

### En el ordenador

Abre el juego en Chrome y pulsa **Jugar en el ordenador** (o la tecla Intro). Haz clic en la pantalla para que el ratón se quede fijo; Esc lo suelta.

| Control | Qué hace |
| --- | --- |
| W A S D o flechas | Andar |
| Ratón | Mirar |
| Barra espaciadora | Saltar (dos veces seguidas: doble salto) |
| Clic izquierdo | Usar la herramienta sobre lo que tienes delante |
| Q | Cambiar entre martillo y espada |
| F o clic derecho | Bola de fuego (con 3 monedas o más) |
| Intro en el panel final | Volver a jugar |

En la pantalla de inicio también puedes empezar un **mundo nuevo** (borra el mundo guardado y el récord) y activar o silenciar el **sonido**.

## Probarlo en local

Desde la carpeta raíz de ClonaKit:

```bash
npm run probar -- pepecraft
```

Se abrirá en http://localhost:3000. Así puedes jugar en el ordenador.

Para probarlo en las gafas desde tu red Wi-Fi, el navegador de las Quest exige `https`:

```bash
npm run probar -- pepecraft --https
```

La herramienta te dirá una dirección del tipo `https://<IP-de-tu-ordenador>:8443`. Ábrela en el navegador de las gafas (con el ordenador y las gafas en la misma Wi-Fi). Como el certificado es propio, el navegador avisará de que la conexión no es privada: acepta para continuar.

El juego necesita conexión a internet para descargar A-Frame la primera vez.

## Publicarlo

Es una web estática: todo está en `index.html`, sin build ni dependencias que instalar. Para publicarlo en Vercel:

1. Sube esta carpeta (`app/`) a un repositorio de GitHub.
2. En Vercel, importa el repositorio con el preset **Other** y sin comando de build.
3. Vercel te da una dirección `https://…vercel.app`: ábrela en las gafas y a jugar.

Cada `git push` publica una versión nueva. Desde ClonaKit, el comando `/desplegar` te guía paso a paso.

## Qué se guarda

En el propio navegador (`localStorage`): la semilla del terreno, los bloques que has cavado y tu mejor tiempo. No se guarda ningún dato personal ni se envía nada a ningún servidor.

## Créditos

- [A-Frame](https://aframe.io) 1.7.0 (incluye Three.js), licencia MIT.
- Todo lo demás (código, texturas, modelos de cajas, música y sonidos) es propio de PepeCraft.
