# Laboratorio-5-Frecuencia-cardiaca-HRV y balance atonomico
𝙞𝙣𝙩𝙧𝙤𝙙𝙪𝙘𝙘𝙞ó𝙣

La variabilidad frecuenciaacardíacadíaca (HRV) es un parámetro fisiológico que permite evaluar el equilibrio entre las ramas simpática y parasimpádela del sistema nervioso autónomo a través del análisis de los intervalos R-R obtenidos de la señal electrocardiográfica (ECG). Este parámetro es una herramienta fundamental en el estudio de la regulación cardíaca, ya que refleja la capacidad del corazón para adaptarse a diferentes estados fisiológicos, como el reposo o la actividad mental. En esta práctica se analizó la HRV mediante técnicaorganismodigital de señales, utilizando herramientas computacionales como Python para el filtrado, segmentación y análisis de los datos, con el fin de comprender cómo las variaciones en la frecuencia cardíaca pueden indicar cambios en la actividad autonómica del organismo.

𝙤𝙗𝙟𝙚𝙩𝙞𝙫𝙤

Identificar los cambios en el balance autonómico a partir del análisis temporal de la variabilidad de la frecuencia cardíaca (HRV), aplicando técnicas de procesamiento digital de señales para el filtrado y estudio de los intervalos R-R, y comparando la respuesta cardíaca en condiciones de reposo y durante la lectura en voz alta, con el propósito de relacionar la actividad simpática y parasimpática en ambos estados fisiológicos.

𝙞𝙢𝙥𝙤𝙧𝙩𝙖𝙘𝙞ó𝙣 𝙙𝙚 𝙡𝙞𝙗𝙧𝙚𝙧𝙞𝙖𝙨

```python
import numpy as np
import matplotlib.pyplot as plt
```

<h1 align="center"><i><b>𝐏𝐚𝐫𝐭𝐞 A 𝐝𝐞𝐥 𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐨𝐫𝐢𝐨</b></i></h1>


**PARTE A - A** 𝙛𝙪𝙣𝙙𝙖𝙢𝙚𝙣𝙩𝙤 𝙩𝙚𝙤𝙧𝙞𝙘𝙤 

En la primera parte de la práctica se realizó una investigación teórica sobre la actividad simpática y parasimpática del sistema nervioso autónomo, su influencia en la frecuencia cardíaca y el concepto de variabilidad de la frecuencia cardíaca (HRV). Además, se estudió cómo la señal electrocardiográfica (ECG) permite obtener los intervalos R-R necesarios para el análisis de la HRV y se revisó el uso del diagrama de Poincaré como herramienta gráfica para evaluar el equilibrio entre la actividad simpática y parasimpáticaEn la primera parte de la práctica se realizó una investigación teórica sobre la actividad simpática y parasimpática del sistema nervioso autónomo, su influencia en la frecuencia cardíaca y el concepto de variabilidad de la frecuencia cardíaca (HRV). Además, se estudió cómo la señal electrocardiográfica (ECG) permite obtener los intervalos R-R necesarios para el análisis de la HRV y se revisó el uso del diagrama de Poincaré como herramienta gráfica para evaluar el equilibrio entre la actividad simpática y parasimpática.

𝟭. 𝘼𝙘𝙩𝙞𝙫𝙞𝙙𝙖𝙙 𝙎𝙞𝙢𝙥𝙖𝙩𝙞𝙘𝙖 𝙮 𝙋𝙖𝙧𝙖𝙨𝙞𝙢𝙥𝙖𝙩𝙞𝙘𝙖 𝙙𝙚𝙡 𝙨𝙞𝙨𝙩𝙚𝙢𝙖 𝙣𝙚𝙧𝙫𝙞𝙤𝙨𝙤 𝙖𝙪𝙩𝙤𝙣𝙤𝙢𝙤

El cuerpo está diseñado para poder mantener un equilibrio perfecto entre la actividad y el descanso ,esto es gracias al sistema nervioso autonomo, ya que este es el encargado de regular muchas de las funciones involuntarias que genera el organismo del cuerpo hconjuntoumano. 
dentro de este sistema se encuentra el sistema nervioso simpático y el sistema nervioso parasimpático los cuales son dos fuerzas opuestas encargadas de trabajar en  para poder mantener el bienestar del cuerpo.
<table>
  <tr>
    <td style="vertical-align: top; text-align: center;">
      <img src="https://github.com/user-attachments/assets/65cc303a-262d-4998-b7ef-1942768a875d" width="700"><br>
      <sub><b>imagen 1.</b> Sistema nervioso simpático.[1] </sub>
    </td>
    <td style="vertical-align: top; padding-left: 15px;">
sistema nervioso simpático: es el encargado de la aceleración de nuestro cuerpo, es decir es el responsable de la activación de la respuesta de huida cuando una persona se enfrenta a una situación de peligro o estrés .Es importante durante el reposo ya que es clave para preparar al cuerpo durante situaciones de emergencia .[2]
El sistema nervioso Simpatico funciona activando diversas vias donde se es evidente el aumento del ritmo cardiaco y respiratorio, presion sanguinea  dilatación de las pupilan,  cambios en el flujo sanguineo para que la sangre salga de la pie, estomago e intestinos para dirigirse hacia el cerebro,  corazón . y los diferentes musculos que sean  necesarios para llevar a cabo esta respuesta ante la actividad Simpatica.
    </td>
  </tr>
</table>



<table>
  <tr>
    <td style="vertical-align: top; text-align: center;">
      <img src="https://github.com/user-attachments/assets/bf0e4117-4f84-4f34-88ca-8376eb56190e" width="400"><br>
      <sub><b>imagen 2.</b> Sistema nervioso parasimpático.[1] </sub>
    </td>
    <td style="vertical-align: top; padding-left: 15px;">
Sistema nervioso  parasimpatico: controla la actividad de los musculo liso cardiaco y las glandulas. Es el  encargado de la respuesta  de descanso  debido a que esta involucrado en relentizar el  ritmo cardiaco , relajar los hemisterios en el tracto gastrointestinal y urinario y aumentar la actividad glandular e  intestinal.[3]como resultado se encuentra que el sistema parasimpatico es el encargado del almacenamiento de energía y la regulación de las funciones del cuerpo  como la digestion y la micción.
    </td>
  </tr>
</table>



𝟮. 𝙀𝙛𝙚𝙘𝙩𝙤 𝙙𝙚 𝙡𝙖 𝙖𝙘𝙩𝙞𝙫𝙞𝙙𝙖𝙙 𝙨𝙞𝙢𝙥𝙖𝙩𝙞𝙘𝙖 𝙙𝙚𝙡 𝙨𝙞𝙨𝙩𝙚𝙢𝙖 𝙣𝙚𝙧𝙫𝙞𝙤𝙨𝙤 𝙖𝙪𝙩𝙤𝙣𝙤𝙢𝙤:

𝟯. 𝙫𝙖𝙧𝙞𝙖𝙗𝙞𝙡𝙞𝙙𝙖𝙙 𝙙𝙚 𝙡𝙖 𝙛𝙧𝙚𝙘𝙪𝙚𝙣𝙘𝙞𝙖 𝙘𝙖𝙧𝙙𝙞𝙖𝙘𝙖 (𝙃𝙍𝘾) 𝙤𝙗𝙩𝙚𝙣𝙞𝙙𝙖 𝙖 𝙥𝙖𝙧𝙩𝙞𝙧 𝙙𝙚 𝙡𝙖 𝙨𝙚𝙣̃𝙖𝙡 𝙚𝙡𝙚𝙘𝙩𝙧𝙤𝙘𝙖𝙧𝙙𝙞𝙤𝙜𝙧𝙖𝙛𝙞𝙘𝙖 (𝙀𝘾𝙂).

La variabilidad de la frecuencia cardíaca (HRV) es un indicador fisiológico que mide las fluctuaciones en el intervalo de tiempo entre latidos consecutivos del corazón, conocidos como intervalos RR. Estos valores se obtienen a través de la señal electrocardiográfica (ECG). Este análisis proporciona información valiosa sobre el equilibrio entre las ramas simpática y parasimpática del sistema nervioso autónomo, responsables de regular la actividad cardíaca (Shaffer y Ginsberg, 2017).

Para calcular la HRV, se registra inicialmente la señal ECG y se identifican los complejos QRS, destacando los picos R, que caracterizan cada ciclo cardíaco. A continuación, se mide el tiempo entre dos picos R consecutivos (intervalo RR). Con esta serie de intervalos, se realiza el análisis de su variabilidad utilizando métodos en el dominio del tiempo o en el dominio de la frecuencia (Malik et al., 1996).

En el dominio del tiempo, los parámetros más habituales son la SDNN (desviación estándar de los intervalos RR) y la RMSSD (raíz cuadrada de la media de las diferencias cuadráticas sucesivas), que reflejan respectivamente la variabilidad global y la influencia del tono vagal. En el dominio de la frecuencia, se analizan componentes espectrales como LF (Low Frequency) y HF (High Frequency), que permiten estudiar el balance entre la actividad simpática y parasimpática. El cociente LF/HF se utiliza como indicador del equilibrio autonómico (Task Force, 1996).

La HRV se ha establecido como una herramienta valiosa tanto en entornos clínicos como en investigaciones. Una alta variabilidad suele asociarse con un sistema cardíaco saludable y una buena capacidad de adaptación fisiológica, mientras que una baja variabilidad puede ser señal de estrés, fatiga o disfunción autonómica. Por esta razón, el análisis de HRV a partir de la señal ECG es considerado un método no invasivo y fiable para evaluar la modulación autonómica del corazón (Shaffer y Ginsberg, 2017).

𝟰. 𝘿𝙞𝙖𝙜𝙧𝙖𝙢𝙖 𝙙𝙚 𝙥𝙤𝙞𝙣𝙘𝙖𝙧𝙚 𝙘𝙤𝙢𝙤 𝙝𝙚𝙧𝙧𝙖𝙢𝙞𝙚𝙣𝙩𝙖  𝙙𝙚 𝙖𝙣𝙖𝙡𝙞𝙨𝙞𝙨 𝙙𝙚 𝙡𝙖 𝙎𝙚𝙣̃𝙖𝙡 𝙍-

<table>
  <tr>
    <td style="vertical-align: top; text-align: center;">
      <img src="https://github.com/user-attachments/assets/9f20fe07-f172-4b1f-92ca-b875e5adee59" width="900"><br>
      <sub><b>imagen 3.</b> diagrama de poincare.[5] </sub>
    </td>
    <td style="vertical-align: top; padding-right: 15px;">
Es una herramienta para el analisis no lineal de la variable de la frecuencia cardiaca , obtenida a partir de la serie R-R , la cual representa los intervalos  de tiempo entre latidos consecutivos del corazón. Estos permiten mediante una transformación matematica representar graficamente la dinamica de la señal cardiaca. En este metodo , cada intervalo R-R se representan en  función del siguiente (RRn+1) generando una serie de puntos en el plano en forma de nube. la forma y dispersion refleja las caracteristicas  dinámicas del sistema cardiovascular permitiendo identificar patronos de regularidad, variabilidad o comportamiento. Este diagrama se presenta de manera bidimencional permitiendo simplificar la dinamica temporal de la señal (como varia la señal a lo largo del tiempo - intervalos entrelatidos de un momento a otro) y visualizar con claridad los patrones generales del comportamiento autonomico.[4][6]
    </td>
  </tr>
</table>

<table>
  <tr>
    <td style="vertical-align: top; padding-left: 15px;">
     Cuando se obtiene una figura en forma de elipse estrecha y alargada, se interpreta como baja variabilidad Esto implica que los intervalos entre latidos cambia muy poco, lo que refleja una menor flexibilidad del sistema nervioso autonomo para adaptarse  a las demandas internas y externas.
Por otro lado una figura más amplia , dispersa  o cercana a una forma  circular indica una alta variabilidad cardiaca  y un mejor equilibrio entre los sistemas Simpatico y parasimpatico. 
En comparación con otros metodos lineales, el diagrama de poincare  ofrece una vision topologica y geometrica de la dinamica cardiaca, permitiendo captar comportamientos no lineales que no se evidenciar mediante estadisticas convencionales. Por ello, esta herramienta se utiliza frecuentemente en el estudio de la serie R-R  para evaluar el control autonomico del corazón en condicion de repaso  estres o enfermedad.[6][7]
    </td>
    <td style="vertical-align: top; text-align: center;">
      <img src="https://github.com/user-attachments/assets/e76da245-3f4a-47bf-9c52-f9a9659ae756" width="1500"><br>
      <sub><b>imagen 4.</b> diagrama de poincare del corazon [8]</sub>
    </td>
  </tr>
</table>

**Ejemplos Relacionados**

| **Tipo de Ritmo**                 | **Descripción Breve**                                                                                           | **Imagen**                                                                                         |
|------------------------------------|------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Ritmo Regular**                  | Intervalos constantes entre latidos, sin variación significativa.                                                | <img width="250" height="300" alt="Ritmo Regular" src="https://github.com/user-attachments/assets/b7ea282d-1fea-4d44-bc72-a54c5e601a19"/> <br> <sub><b>Imagen 5.</b> Diagrama y gráficas en ritmos regular (normal) [9]</sub>|
| **Ritmo Regular con Extrasístoles**| Latidos adicionales ocasionan irregularidades en los intervalos, visibles en el tacograma y diagrama de Poincaré.  | <img width="250" height="300" alt="Ritmo con Extrasístoles" src="https://github.com/user-attachments/assets/bee8d739-42df-4aa0-8e11-220593a7bb77"/> <br> <sub><b>Imagen 6.</b> Diagrama y gráficas en ritmo regular latidos ectópicos [9]</sub>|
| **Fibrilación Auricular**          | Patrones caóticos e irregulares, con intervalos muy variables y dispersión de puntos en el diagrama de Poincaré. | <img width="250" height="300" alt="Fibrilación Auricular" src="https://github.com/user-attachments/assets/4d3436bc-ed4f-4ebc-860f-13a8c78edac2"/> <br> <sub><b>Imagen 7.</b> Diagrama y gráficas en fibrilación auricular [9]</sub>|



**variabilidad e intereptacion del diagrama de poincare**

<div align="center">

<table style="width: 70%; text-align: center;">
  <tr>
    <th>Forma del Diagrama</th>
    <th>Variabilidad</th>
    <th>Sistema Nervioso Involucrado</th>
    <th>Interpretación</th>
  </tr>

  <tr>
    <td>Elipse estrecha y alargada</td>
    <td>Baja variabilidad</td>
    <td>Predomina el simpático</td>
    <td>Menor flexibilidad del corazón, poca adaptación.</td>
  </tr>

  <tr>
    <td>Elipse amplia</td>
    <td>Variabilidad moderada</td>
    <td>Equilibrio simpático–parasimpático</td>
    <td>Buena respuesta, aunque con cierta rigidez.</td>
  </tr>

  <tr>
    <td>Forma circular o dispersa</td>
    <td>Alta variabilidad</td>
    <td>Fuerte equilibrio autónomo</td>
    <td>El corazón se adapta muy bien a los cambios.</td>
  </tr>

  <tr>
    <td>Puntos irregulares</td>
    <td>Variabilidad baja o irregular</td>
    <td>Desbalance autónomo</td>
    <td>Relacionado con estrés o posibles alteraciones.</td>
  </tr>

</table>

</div>
A su vez tambien se obtienen los parámetros SD1 y SD2. El primero está asociado a las diferencias entre intervalos RR consecutivos. El segundo está relacionado con la desviación estándar de los intervalos RR.

| **Parámetro** | **Descripción**                                          | **Relación con la variabilidad cardíaca**                     | **Significado en términos del sistema nervioso autónomo**                 |
|---------------|----------------------------------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------|
| **SD1**       | Desviación estándar en la dirección perpendicular a la línea de identidad. | Asociado a la variabilidad a corto plazo (fluctuaciones rápidas). | Refleja la **actividad parasimpática** (control del sistema nervioso autónomo que regula el descanso y la recuperación). |
| **SD2**       | Desviación estándar en la dirección paralela a la línea de identidad. | Asociado a la variabilidad a largo plazo (fluctuaciones lentas). | Refleja el **equilibrio entre los sistemas simpático y parasimpático**. |


**Plan de acccion** 

A continuación, se presentará el plan de acción que se implementará para abordar los puntos clave del análisis. Este plan tiene como objetivo facilitar la comprensión de los resultados y definir las siguientes acciones a seguir.

<p align="center">
  <img src="https://github.com/user-attachments/assets/33e4c00e-feb1-4874-a904-b7d704122998" width="300">
</p>

**PARTE A - B**
Para esta parte del laboratorio se detallará el proceso para la adquisición de la señal ECG. Este paso incluye la selección de un sujeto de prueba, la grabación de la señal durante un período específico y la verificación de los parámetros técnicos adecuados, como la frecuencia de muestreo y los niveles de cuantificación.

| **Parámetro**                       | **Valor/Registro**                     |
|-------------------------------------|----------------------------------------|
| **Identificación del Sujeto**       | Sujeto X                               |
| **Fecha de Registro**               | 14 de noviembre de 2025                 |
| **Duración Total de la Adquisición**| 4 minutos                              |
| **Duración Fase Inmóvil y Silenciosa** | 2 minutos                             |
| **Duración Fase de Lectura**        | 2 minutos                              |
| **Frecuencia de Muestreo**          | 2000 Hz                                |
| **Niveles de Cuantificación**       | 12 bits                                |
| **Instrumento/Equipo Utilizado**    | Módulo AD8232                          |
| **Estado del Sujeto**               | 20 años, peso 65 kg, estatura 1.58 m, femenino, en reposo y sin molestias |
| **Observaciones**                   | Ninguna                                 |

```python
import nidaqmx
from nidaqmx.constants import AcquisitionType
import matplotlib.pyplot as plt
import numpy as np
from scipy.signal import butter, filtfilt, iirnotch

# ------------------ Parámetros ------------------
fs = 2000
canal = "Dev5/ai0"
N = fs * 1      # ventana de 1 segundo
senal_total = []

# ---------- FILTRO PASA-BANDA 1–40 Hz ----------
lowcut_freq = 1.0  # Hz
highcut_freq = 40.0 # Hz
b_bp, a_bp = butter(4, [lowcut_freq/(fs/2), highcut_freq/(fs/2)], btype='bandpass')

# ---------- FILTRO NOTCH 60 Hz ----------
b_notch, a_notch = iirnotch(60/(fs/2), 30)

def aplicar_filtro(x):
    # PASA-BANDA
    x = filtfilt(b_bp, a_bp, x)

    # NOTCH
    x = filtfilt(b_notch, a_notch, x)

    return x

# ---------- Ventana gráfica externa ----------
plt.ion()   # modo interactivo
fig, ax = plt.subplots()

xdata = np.arange(N)
ydata = np.zeros(N)

linea, = ax.plot(xdata, ydata)
ax.set_ylim(-1, 1)
ax.set_xlim(0, N)
ax.grid(True)
ax.set_title("ECG en tiempo real")
ax.set_xlabel("Muestra")
ax.set_ylabel("Voltaje (V)")

# --------------- ADQUISICIÓN DAQ ---------------
with nidaqmx.Task() as task:
    task.ai_channels.add_ai_voltage_chan(canal)
    task.timing.cfg_samp_clk_timing(fs, sample_mode=AcquisitionType.CONTINUOUS)

    print("Adquiriendo... cerrar ventana o Ctrl+C para detener.")

    try:
        while plt.fignum_exists(fig.number):
            # Leer 1 segundo
            bloque = task.read(number_of_samples_per_channel=N)
            bloque = np.array(bloque, dtype=float)

            # Filtrar
            bloque = aplicar_filtro(bloque)

            # Guardar
            senal_total.extend(bloque)

            # Actualizar gráfica
            linea.set_ydata(bloque)
            ax.set_ylim(bloque.min()*1.2, bloque.max()*1.2)

            fig.canvas.draw()
            fig.canvas.flush_events()

    except KeyboardInterrupt:
        print("Adquisición detenida manualmente.")

# ---------- Post-procesamiento ----------
senal_total = np.array(senal_total)
t = np.arange(len(senal_total)) / fs

plt.ioff()
plt.figure()
plt.plot(t, senal_total)
plt.title("ECG completo filtrado")
plt.xlabel("Tiempo (s)")
plt.ylabel("Voltaje (V)")
plt.grid(True)
plt.show()

# Guardar archivo
np.savetxt("1ECGANTOCOMPLETO.txt", np.column_stack((t, senal_total)))
print("Guardado como 1ECGANTOCOMPLETO.txt")
```

Este código adquiere señales de un electrocardiograma (ECG) en tiempo real utilizando un dispositivo de adquisición de datos (DAQ) con una frecuencia de muestreo de 2000 Hz. La señal se filtra en dos etapas: primero con un filtro pasa-banda (1-40 Hz) para eliminar el ruido de baja y alta frecuencia, y luego con un filtro notch a 60 Hz para eliminar la interferencia de la red eléctrica. La señal filtrada se actualiza en tiempo real en un gráfico interactivo, y al finalizar la adquisición, se guarda la señal completa en un archivo de texto. La adquisición continúa hasta que el usuario la detiene manualmente.

```python
data = np.loadtxt('/content/1ECGSOFICOMPLETO.txt')
t = data[:, 0]  # Tiempo (en segundos)
senal = data[:, 1]  # Señal ECG

plt.figure(figsize=(10, 6))
plt.plot(t, senal, label="ECG "¨,color="#C8A2C8")
plt.title("ECG Adquirido desde DAQ")
plt.xlabel("Tiempo (s)")
plt.ylabel("Voltaje (V)")
plt.grid(True)
plt.legend()
plt.show()
```
Este código usa NumPy para cargar los datos del archivo .txt con np.loadtxt() (carga el tiempo y la señal ECG desde el archivo). Luego, usa Matplotlib para graficar la señal con plt.plot(), donde se configura el eje x como el tiempo y el eje y como la señal ECG. Se añaden etiquetas con plt.xlabel() y plt.ylabel(), se establece el título con plt.title(), y se activa la cuadrícula con plt.grid() para mejorar la visualización.

**resultado*
<p align="center">
<img width="600" height="500" alt="image" src="https://github.com/user-attachments/assets/d10861c1-9e8f-4f2e-bda0-a89f1a1269dc" />
</p>
















<h1 align="center"><i><b>Bibliografia</b></i></h1>
[1]Researchgate.net.de https://www.researchgate.net/figure/Figura-173-Los-sistemas-simpatico-y-parasimpatico_fig2_313160220
[2]Sistema nervioso simpático. (2023, 30 octubre). Kenhub. https://www.kenhub.com/es/library/anatomia-es/sistema-nervioso-simpatico
[3]Sistema nervioso parasimpático. (2023, 30 octubre). Kenhub. https://www.kenhub.com/es/library/anatomia-es/sistema-nervioso-parasimpatico
[4]Fishman, M., Jacono, F. J., Park, S., Jamasebi, R., Thungtong, A., Loparo, K. A., & Dick, T. E. (2012). A method for analyzing temporal patterns of variability of a time series from Poincaré plots. Journal Of Applied Physiology, 113(2), 297-306. https://doi.org/10.1152/japplphysiol.01377.2010
[5]Researchgate.net.de https://www.researchgate.net/figure/Figura-95-Diagramas-de-Poincare-y-parametros-tipicos-calculados-a-partir-de-la-senal-ECG_fig18_39569851
[6]Hrv_Admin. (s. f.). Understanding the Poincaré plot – HRV Health. https://hrvhealth.org/blog/?p=124
[7] CH González Obregón Upc.edu.(2002), de https://upcommons.upc.edu/server/api/core/bitstreams/eafd6950-b60c-462d-8eeb-1c6e1ee97891/content
[8]Researchgate.net.de https://www.researchgate.net/figure/Figura-94-Diagrama-de-Poincare-de-una-serie-RR_fig17_39569851
[9]Academia FibriCheck(2023) de https://academy.fibricheck.com/hc/en-be/articles/9020344305564-Chapter-8-Differentiating-regular-and-irregular-PPG-recordings
° Malik, M., et al. (1996). Heart rate variability: Standards of measurement, physiological interpretation, and clinical use. Circulation, 93(5), 1043–1065.

° Shaffer, F., & Ginsberg, J. P. (2017). An overview of heart rate variability metrics and norms. Frontiers in Public Health, 5, 258.

° Task Force of the European Society of Cardiology and the North American Society of Pacing and Electrophysiology. (1996). Heart rate variability: Standards of measurement, physiological interpretation and clinical use. Circulation, 93(5), 1043–1065.
