# UNIDAD 3 : "Integración Audio-Visual"  

## BITÁCORA

- En esta actividad realicé una conexión entre Strudel y TouchDesigner para relacionar un loop musical con una visual generativa.

- Usé el mismo código hecho en la Unidad 1, pero con breves modificaciones con el fin de que sea posible el enviar información desde Strudel hacia TouchDesigner. Esto fue gracias al OSC, quien es quien se encarga de enviar eventos de la batería hacia TouchDesigner, asignando identificadores como drum_bd, drum_cp y drum_hh.

- En TouchDesigner utilicé Strudel Visual Toolkit para recibir y organizar estos mensajes. Para la interacción visual seleccioné el evento drum_bd, correspondiente al bombo de la batería.

- El evento recibido se transforma en una señal que controla la escala de la composición mediante un Transform TOP. De esta manera, la visual cambia de tamaño siguiendo los golpes del bombo mientras la música se reproduce desde Strudel.

- El objetivo principal de la actividad fue experimentar con una integración sencilla entre audio, eventos musicales y gráficos generativos en tiempo real.

## CÓDIGO ACTUALIZADO

``` js
const { visualid } = createParams('visualid')

setcpm(60/4)

let drum = stack(
  s("hh").beat("0, 2, 4, 6, 7, 8, 10, 12, 13, 14, 15",16)
    .visualid("drum_hh"),

  s("cp").beat("2, 6, 10, 14",16)
    .visualid("drum_cp"),

  s("bd").beat("0, 2, 4, 6, 8, 10, 12, 14",16)
    .visualid("drum_bd")
).bank("RolandTr909")

let melody = note("[c3 ~ c3 ~ c3 ~ c3 g3 eb3 ~ eb3 ~ d3 f3 d3 g3]")
  .sound("sawtooth")
  .lpf(20000)
  .lpq(8)
  .legato(1);

let bassline = note("[c2 ~ c2 ~ c2 ~ c2 g2 e2 ~ e2 ~ d2 f2 d2 g2]")
  .sound("triangle")
  .gain(2)
  .legato(0.5);

let electric_bass = note("[~ c2 ~ c2 ~ c2 ~ c2 ~ eb2 ~ eb2 ~ d2 ~ g2]")
  .sound("gm_electric_bass_finger")
  .gain(0.2)
  .legato(1);

$drum: stack(drum, drum.osc())
$:melody
$:bassline
$:electric_bass
```
