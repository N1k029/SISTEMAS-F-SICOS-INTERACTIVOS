# UNIDAD 1: "AUDIO"


## BITÁCORA

- Antes de comenzar a realizar el código, comencé a jugar con el programa learning music.ableton y llegué a la idea de querer recrear la canción de Madagascar: “I Like to Move it”  
- Busqué un pequeño tutorial para poder construir la pieza lo más fidedigna posible dentro de learning music.abelton.  
- Dentro de las funciones que me ofrecía abelton, usé herramientas clave como:  

    Make beats: Para entender y maquetar la base rítmica de la percusión.   
    Play with Chords: Para explorar la progresión armónica y el movimiento de la canción.   
    Play with Baselines: Para definir el patrón del bajo y sus acentos.  



Tutorial:  
["I Like to Move it"l]([https://www.youtube.com/@Switch-Angel](https://youtu.be/_7FRyllNKak?si=qMhHgGopsbw1jRct))

<img width="1667" height="851" alt="Captura de pantalla 2026-07-23 113539" src="https://github.com/user-attachments/assets/63ed5eb5-b696-4a90-b292-3ae4b6d930a3" />  

<img width="1687" height="897" alt="Captura de pantalla 2026-07-23 132429" src="https://github.com/user-attachments/assets/b76d124a-7f5f-4d5e-bca5-fe7b035ae965" />

<img width="1712" height="915" alt="Captura de pantalla 2026-07-23 141649" src="https://github.com/user-attachments/assets/2cf82882-f767-4ebb-a952-65aae4449ad7" />


## CÓDIGO


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



