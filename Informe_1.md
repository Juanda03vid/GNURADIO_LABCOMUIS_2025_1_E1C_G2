# Laboratorio de Comunicaciones
## Universidad Industrial de Santander

Utilice esta [plantilla](#integrantes) para presentar sus informes de laboratorio. 

Al final de la plantilla encontrará algunos ejemplos para enriquecer su informe, incluyendo cómo insertar imágenes, tablas y ecuaciones, así como generar hipervínculos a su repositorio o al propio informe. Ir a [ejemplos en Markdown](#ejemplos-usando-markdown)

### Importante

- En caso de utilizar herramientas de Inteligencia Artificial para asistencia en la redacción, análisis o cualquier otra tarea, de debe especificar en la sección de **Declaración de Originalidad y Responsabilidad** aclarando el alcance y propósito de su uso.
- Cualquier omisión en la declaración del uso de IA o la presentación de contenido plagiado será penalizado con nota de 0.0 y reporte a la coordinación del programa.
- Si emplea referencias disponibles en línea, agregue los hipervínculos respectivos.  

---
# Práctica 1: Mediciones de Potencia y Frecuencia

### Integrantes
- **Juan David Gil Silva** - 2224031
- **Christian Camilo Ellis Jimenez** - Código

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
06 de Marzo de 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Uso de IA: [Indicar si se usó IA y para qué aspectos específicos, por ejemplo: "Se utilizó ChatGPT para reformular secciones del texto y verificar gramática, pero el contenido técnico fue desarrollado íntegramente por los autores."]

---
## Contenido

### Resumen
En esta práctica el objetivo es aprender a usar las herramientas que tenemos en el laboratorio, un software definido por radio (SDR)GNU Radio, equipos de medición como el USRP2920, el osciloscopio R&S RTB2004 y el analizador de espectros R&S FPC1000. Se llevaron a cabo tres actividades: Revisión de Especificaciones de los Equipos, Simulación de Señales en GNU Radio, Transmisión y Medición de Señales con el USRP 2920. Con estas actividades analizamos y comparamos la simulación con la medición real de parámetros clave cómo el ancho de banda(BW), piso de ruido, etc. 

**Palabras clave:** SDR, GNU Radio, BW 

### Introducción
Cada práctica contará con preguntas orientadoras para la elaboración de la introducción. Por ejemplo: 
- ¿Qué tan importante es la teoría de muestreo en el procesamiento de señales?
- ¿Cuáles son los principales potenciales de GNURADIO en el laboratorio de comunicaciones?
- ¿Qué pasa cuando se alcanza el límite de Nyquist?
- ¿Qué tan alta debe ser la relación entre la frecuencia de muestreo y la frecuencia de la señal para visualizar la señal correctamente?
- ¿Cuándo es importante interpolar una señal?
- ¿Cuándo es importante diezmar una señal?
- ¿Qué pasa cuando se asigna una frecuencia de muestreo inadecuada?

### Procedimiento
### Actividad 1
Revisamos las especificaciones de los equipos que tenemos en el laboratorio y estas fueron las 5 que consideramos que son las mas importantes de cada uno.
### USRP-2920
- Frequency Range 50MHz to 2.2 GHz.
- Maximum instantaneous real-time bandwidth:
  16-bit sample width 20 MHz y 8-bit sample width 40 MHz.
- Digital-to-analog converter (DAC) 2 channels, 400 MS/s, 16 bit.
- Gain range 0dB to 31dB.
- Total power, typical operation (
Typical 12 W to 15 W,
Maximum).

### Osciloscopio R&S RTB2004
- Number of oscilloscope channels 2.
- Bandwidth in MHz 50, 70, 100, 200, 300.
- Max. sampling rate in Gsample/s 1/channel, 2 interleaved.
- MSO 8 channels, 1 Gsample/s.
- Generator(s) 1 generator, 4-bit pattern generator.

### Analizador de Espectros R&S FPC1000
- Rango de frecuencias R&S®FPC1000 de 5 kHz a 1 GHz.
- Ancho de banda de resolución de 1 Hz a 3 MHz en secuencia de 1/3.
- Nivel de ruido promedio visualizado (DANL) Atenuación de RF 0 dB, terminaciónde 50 Ω, ancho de banda de resolución (RBW) = 100 Hz, VBW = 10 Hz, detector de muestra, escala logarítmica, normalizado a 1 Hz.
- Resolución de frecuencia 1 Hz.
- Respuesta en frecuencia (de +20°C a +30°C) 100 kHz ≤ f < 10 MHz.

  ### Actividad2
  Utilizamos GNU Radio para simular funciones y ver cómo se comoprtan en el tiempo y la frecuencia. Generamos las siguientes señales, dientes de sierra, cuadrada, triangular, coseno y seno.

  ### Actividad3
  

 
  
Debe basarse en las acciones efectivamente realizadas durante el laboratorio, describiendo los procesos realizados y los resultados obtenidos. Para cada práctica se pueden brindar preguntas orientadoras o pasos a seguir para establecer lo que se espera lograr/estudiar/analizar/obtener/comparar. Por ejemplo:
- Describa los procesos realizados en el laboratorio  y los resultados obtenidos.
- ¿Cómo se alcanza el límite de Nyquist y que pasa cuando se disminuye de este?
- ¿Por qué al interpolar una señal en GNURADIO su frecuencia disminuye?
- ¿Por qué al diezmar una señal en GNURADIO su frecuencia aumenta?
- ¿Cómo se puede determinar la frecuencia máxima de una señal desde lo experimental?
- ¿Qué le sucede a una señal de audio cuando no se respeta el teorema de Nyquist?
- Describa las funciones logradas con el Ecualizador desarrollado con GNURadio.

### Conclusiones
Se sintetizan los principales aportes y puntos relevantes de la práctica, evitando repetir lo ya consignado en las otras secciones del informe. 

### Referencias
Ejemplo de referencia:

- [Proakis, 2014] J. Proakis, M. Salehi. Fundamentals of communication systems. 2 ed. England: Pearson Education Limited, 2014. p. 164-165, 346. Chapter 5 In: [Biblioteca UIS](https://uis.primo.exlibrisgroup.com/permalink/57UIDS_INST/63p0of/cdi_askewsholts_vlebooks_9781292015699)

---
# Ejemplos usando Markdown

Volver al [INICIO](#laboratorio-de-comunicaciones)

## Inclusión de Imágenes
### Imagen de referencia dentro del repositorio:
![Networking](my%20file/test.png)

### Imagen de fuente externa
![GNU Radio logo](https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png)

### Uso de html para cambiar escala de la imagen
<img src="https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png" alt="GNU Radio Logo" width="300">

## Creación de hipevínculos 
- [Aprende Markdown](https://markdown.es/)
- [Más acerca de Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Abrir documento en el repositorio](my%20file/test_file.txt). Si hay espacios en la ruta de su archivo, reemplácelos por `%20`.
- Ir a una sección de este documento. Por ejemplo: [Ir a Contenido](#contenido) Tenga en cuenta escribir el título de la sección en minúsculas y los espacios reemplazarlos por guiones.
## Uso de Expresiones Matemáticas
Se pueden incluir ecuaciones en el archivo `README.md` utilizando sintaxis similar a [LaTeX](https://manualdelatex.com/tutoriales/ecuaciones):

### Ecuaciones en Línea
```
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.
```
**Salida renderizada:**
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.

### Ecuaciones en Bloque
```
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$
```
**Salida renderizada**
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$

## Creación de Tablas

**Tabla 1.** Ejemplo de tabla en Markdown.

| Parámetro | Valor |
|-----------|-------|
| Frecuencia (Hz) | 1000 |
| Amplitud (V) | 5 |
| Ciclo útil (%) | 50 |

## Inclusión de código

```python
def hello_world():
    print("Hello, World!")
```

También es posible resaltar texto tipo código como `print("Hello, World!")`.

---

Volver al [INICIO](#laboratorio-de-comunicaciones)
