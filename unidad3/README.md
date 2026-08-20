# UNIDAD 3 : "Integración Audio-Visual"  

## BITÁCORA

- En esta actividad realicé una conexión entre Strudel y TouchDesigner para relacionar un loop musical con una visual generativa.

- Usé el mismo código hecho en la Unidad 1, pero con breves modificaciones con el fin de que sea posible el enviar información desde Strudel hacia TouchDesigner. Esto fue gracias al OSC, quien es quien se encarga de enviar eventos de la batería hacia TouchDesigner, asignando identificadores como drum_bd, drum_cp y drum_hh.

- En TouchDesigner utilicé Strudel Visual Toolkit para recibir y organizar estos mensajes. Para la interacción visual seleccioné el evento drum_bd, correspondiente al bombo de la batería.

- El evento recibido se transforma en una señal que controla la escala de la composición mediante un Transform TOP. De esta manera, la visual cambia de tamaño siguiendo los golpes del bombo mientras la música se reproduce desde Strudel.

- El objetivo principal de la actividad fue experimentar con una integración sencilla entre audio, eventos musicales y gráficos generativos en tiempo real.
