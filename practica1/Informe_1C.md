**Laboratorio de Comunicaciones**

**Universidad Industrial de Santander**

**Práctica 1: Mediciones de Potencia y Frecuencia**

**Integrantes**

- **Juan David Gil Silva** - 2224031
- **Christian Camilo Ellis Jimenez** - 2192274

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones

Universidad Industrial de Santander

**Fecha**

06 de Marzo de 2025

**Declaración de Originalidad y Responsabilidad**

Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento.

Se utilizó ChatGPT para reformular secciones del texto y verificar gramática, pero el contenido técnico fue desarrollado íntegramente por los autores.

**Contenido**

**Resumen**

En esta práctica el objetivo es aprender a usar las herramientas que tenemos en el laboratorio, un software definido por radio (SDR)GNU Radio, equipos de medición como el USRP2920, el osciloscopio R&S RTB2004 y el analizador de espectros R&S FPC1000. Se llevaron a cabo tres actividades: Revisión de Especificaciones de los Equipos, Simulación de Señales en GNU Radio, Transmisión y Medición de Señales con el USRP 2920. Con estas actividades analizamos y comparamos la simulación con la medición real de parámetros clave cómo el ancho de banda(BW), piso de ruido, etc.

**Palabras clave:** SDR, GNU Radio, BW

**Introducción**

En esta práctica se utilizaron herramientas como GNU Radio, el USRP2920, el osciloscopio R&S RTB2004 y el analizador de espectro R&S FPC1000 para realizar mediciones de potencia y frecuencia en señales generadas y transmitidas. Se realizaron tres actividades: revisión de especificaciones de equipos, simulación de señales en GNU Radio y transmisión de señales con el USRP2920. Se analizaron parámetros clave como ancho de banda, piso de ruido y relación señal-ruido (SNR), comparando resultados teóricos con mediciones reales. La práctica permitió comprender el impacto de las variaciones en la frecuencia de muestreo, amplitud y fase, reforzando conceptos teóricos y desarrollando habilidades prácticas en el manejo de equipos y software especializados.

**Procedimiento**

**Actividad 1**

Revisamos las especificaciones de los equipos que tenemos en el laboratorio y estas fueron las 5 que consideramos que son las más importantes de cada uno.

**USRP-2920**

• Frequency Range 50MHz to 2.2 GHz.

• Maximum instantaneous real-time bandwidth: 16-bit sample width 20 MHz y 8-bit sample width 40 MHz.

• Digital-to-analog converter (DAC) 2 channels, 400 MS/s, 16 bit.

• Gain range 0dB to 31dB.

• Total power, typical operation (Typical 12W to 15W, Maximum).

**Osciloscopio R&S RTB2004**

• Number of oscilloscope channels 2.

• Bandwidth in MHz 50, 70, 100, 200, 300.

• Max. sampling rate in Gsample/s 1/channel, 2 interleaved.

• MSO 8 channels, 1 Gsample/s.

• Generator(s) 1 generator, 4-bit pattern generator.

**Analizador de Espectros R&S FPC1000**

• Rango de frecuencias R&S®FPC1000 de 5 kHz a 1 GHz.

• Ancho de banda de resolución de 1 Hz a 3 MHz en secuencia de 1/3.

` `• Nivel de ruido promedio visualizado (DANL) Atenuación de RF 0 dB, terminaciónde 50 Ω, ancho de banda de resolución         (RBW) = 100 Hz, VBW = 10 Hz, detector de muestra, escala logarítmica, normalizado a 1 Hz.

`        `• Resolución de frecuencia 1 Hz.

`        `• Respuesta en frecuencia (de +20°C a +30°C) 100 kHz ≤ f < 10 MHz.

**Actividad 3**

Para transmitir la señal al USRP, desde el flujograma que tenemos en GNU Radio activamos el bloque USRP Sink ya que este bloque es el que envía la señal al USRP, simulamos y tomamos dos muestras cambiando la frecuencia de muestreo de 10kHz a 20kHz. Señal Coseno con samp\_rate de 10 kHz.




![image](https://github.com/user-attachments/assets/fbc57c5b-3bc1-4ef8-b009-e7c936df0822)

***Imagen 1.** Señal Coseno con un samp\_rate de 10 kHz*


![image](https://github.com/user-attachments/assets/85192292-dc04-40d6-b7f1-54201fa10e6d)

***Imagen 2.** Señal Coseno con un samp\_rate de 20 kHz*


![image](https://github.com/user-attachments/assets/36ea402f-0045-49e1-8c86-1cf57e2d10da)

***Imagen 3.** Señal Coseno con un samp\_rate de 1 MHz*

Lo siguiente es conectar la salida del USRP al analizador de espectros, utilizamos una función Coseno con una frecuencia de 100 MHz para encontrar el ruido de piso normalizado.

![image](https://github.com/user-attachments/assets/eed0a664-6f60-4226-93fa-77937b52c4b7)


***Imagen 4.** Señal Coseno con una frecuencia de 100 MHz.*


![image](https://github.com/user-attachments/assets/66365476-c0cd-4c65-b950-401d949ebe27)

***Imagen 5.** Señal Coseno con una frecuencia portadora de 100 MHz*

*De la **Imagen 5.**  podemos decir que el piso de ruido normalizado está alrededor de -100 dBm. Ahora lo vamos a hallar con la fórmula de Noise Floor Nf[dBm/Hz] = Pnref[dBm] -10log(RBW/1Hz) .* Si miramos en la **Imagen 5.** mi Pnref sería aproximadamente -97 dBm; también tenemos RBW = 10 khZ. Con esto tenemos que 

*Noise Floor = -137 dBm*


Modificamos algunos parámetros para analizar el cambio que tiene en las señales usadas.

![image](https://github.com/user-attachments/assets/dd4fd9b1-2646-4fcf-9105-0b1a27eac501)

***Imagen 6.** Señal Coseno con una frecuencia de 2 kHz*

![image](https://github.com/user-attachments/assets/98e396ac-f9ac-4e8b-a1b2-a28e93337846)

***Imagen 7.** Señal Coseno con una frecuencia de 2 kHz*

![image](https://github.com/user-attachments/assets/8c2fa13b-2d0e-49b4-b783-03481fca1eb2)


***Imagen 8.** Señal Coseno con una frecuencia de 1kHz*


![image](https://github.com/user-attachments/assets/123cb09a-7ef8-47bd-9248-30729796fa8f)


***Imagen 9.** Señal Coseno con una frecuencia de 1kHz*

![image](https://github.com/user-attachments/assets/8c7c0fc2-6c5f-4287-b0ef-2d71fc2654ff)


***Imagen 10.** Señal Cuadrada con una frecuencia de 2kHz*

![image](https://github.com/user-attachments/assets/9c606a80-ccd6-431d-880d-f638c9c3d1df)


***Imagen 11.** Señal Cuadrada con una frecuencia de 2kHz*

![image](https://github.com/user-attachments/assets/49d212d4-605d-42a1-8d33-5a63b3e2f31f)

***Imagen 12.** Señal Coseno con una amplitud y fase modificadas*

![image](https://github.com/user-attachments/assets/6fffa19d-6ed1-4387-baf1-cd08e0b96521)

***Imagen 13.** Señal Coseno con una amplitud y fase modificadas*

![image](https://github.com/user-attachments/assets/a43e58e5-43ac-4ca8-8617-11907b26890d)

***Imagen 14.** Potencia medida de una señal Coseno de 1kHz de frecuencia*

![image](https://github.com/user-attachments/assets/e1860399-e547-4a7d-a580-00652bbc02c4)

***Imagen 15.** Ancho de banda y SNR para una señal FM*

Cálculo de la relación señal a ruido SNR para algunas señales generadas en esta práctica.

- Señal Coseno ***Imagen 7*** 

  SNR = P señal - P ruido [dBm]  ***=*** -54 - (-137) = 83 dBm

- Señal Cuadrada ***Imagen 11***

  SNR = P señal - P ruido [dBm]  ***=*** -54 - (-90) = 36 dBm

- Señal Coseno ***Imagen 13***

  SNR = P señal - P ruido [dBm]  ***=*** -52-(-100) = 48 dBm

**Conclusiones**

En esta práctica se evidenció que las simulaciones en GNU Radio ofrecen resultados ideales, libres de ruido, mientras que las mediciones reales con el USRP2920 reflejan la degradación de las señales debido a interferencias y limitaciones de los equipos disponibles en el laboratorio, por tanto, en las señales observadas se pudo evidenciar un alto porcentaje de ruido que alteraba la señal analizada, logrando así contrastar la señal digital ofrecida por el simulador con la señal real observada en el instrumento.

El osciloscopio permitió analizar las señales en el dominio del tiempo, mientras que el analizador de espectros proporcionó detalles en el dominio de la frecuencia, validando conceptos como las series de Fourier. La relación señal-ruido (SNR) resultó ser un parámetro clave, variando según el tipo de señal y el entorno. Se observó que el piso de ruido afecta la sensibilidad del sistema, dificultando la detección de señales débiles. Para mejorar las mediciones, se recomienda optimizar la calibración de los equipos, reducir interferencias y enfocarse en las componentes de mayor potencia del espectro.


**Referencias**

- Farnell. (s.f.). R&S®FPC1000 Analizador de espectro. Recuperado el 5 de marzo de 2025, de <https://www.farnell.com/datasheets/2342799.pdf>

- Test Equipment HQ. (s.f.). Rohde & Schwarz RTB2004 datasheet. Recuperado el 5 de marzo de 2025, de <https://www.testequipmenthq.com/datasheets/Rohde-Schwarz-RTB2004-Datasheet.pdf>

- Test Dynamics. (s.f.). USRP2920 datasheet. Recuperado el 5 de marzo de 2025, de <http://www.testdynamics.co.za/Product/PDF/USRP2920.pdf>

