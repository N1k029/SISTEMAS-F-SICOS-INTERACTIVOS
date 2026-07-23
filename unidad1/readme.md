# UNIDAD 1: "AUDIO"

asdasdsasdasdasdsasdasdass  
eeeeeeeeeeeeeeeeeeeeeeeeeeeee


Tutorial:

[Canal de Switch Angel](https://www.youtube.com/@Switch-Angel)

<img width="865" height="347" alt="image" src="https://github.com/user-attachments/assets/6e797d30-e350-4d0a-9f4c-f3be2acdba3e" />


## Subsecc H2


``` js
setcpm(60/4)

let drum = stack(
  s("hh").beat("0, 2, 4, 6, 7, 8, 10, 12, 13, 14, 15",16),
  s("cp").beat("2, 6, 10, 14",16),
  s("bd").beat("0, 2, 4, 6, 8, 10, 12, 14",16)
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

$:drum
$:melody
$:bassline
$:electric_bass
```





### SubSubsec H3


## Subsecc H2 2

### SubSubsec H3 2


