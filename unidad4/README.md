# UNIDAD 4: "Superficie de Control"

## BITÁCORA

## CÓDIGO ACTUAALIZADO

``` js
const { visualid } = createParams('visualid')

setcpm(60/4)

let drum = stack(
  s("hh").beat("0, 2, 4, 6, 7, 8, 10, 12, 13, 14, 15", 16)
    .visualid("drum_hh"),

  s("cp").beat("2, 6, 10, 14", 16)
    .visualid("drum_cp"),

  s("bd").beat("0, 2, 4, 6, 8, 10, 12, 14", 16)
    .visualid("drum_bd")
).bank("RolandTr909")

let melody = note("[c3 ~ c3 ~ c3 ~ c3 g3 eb3 ~ eb3 ~ d3 f3 d3 g3]")
  .sound("sawtooth")
  .lpf(20000)
  .lpq(8)
  .legato(1)

let bassline = note("[c2 ~ c2 ~ c2 ~ c2 g2 e2 ~ e2 ~ d2 f2 d2 g2]")
  .sound("triangle")
  .gain(2)
  .legato(0.5)

let electric_bass = note("[~ c2 ~ c2 ~ c2 ~ c2 ~ eb2 ~ eb2 ~ d2 ~ g2]")
  .sound("gm_electric_bass_finger")
  .gain(0.2)
  .legato(1)

$drum: stack(drum, drum.osc())
$:melody
$:bassline
$:electric_bass
