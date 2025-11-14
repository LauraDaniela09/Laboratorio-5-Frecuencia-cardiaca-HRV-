# Laboratorio-5-Frecuencia-cardiaca-HRV
𝙞𝙣𝙩𝙧𝙤𝙙𝙪𝙘𝙘𝙞ó𝙣

La variabilidad frecuenciaacardíacadíaca (HRV) es un parámetro fisiológico que permite evaluar el equilibrio entre las ramas simpática y parasimpádela del sistema nervioso autónomo a través del análisis de los intervalos R-R obtenidos de la señal electrocardiográfica (ECG). Este parámetro es una herramienta fundamental en el estudio de la regulación cardíaca, ya que refleja la capacidad del corazón para adaptarse a diferentes estados fisiológicos, como el reposo o la actividad mental. En esta práctica se analizó la HRV mediante técnicaorganismodigital de señales, utilizando herramientas computacionales como Python para el filtrado, segmentación y análisis de los datos, con el fin de comprender cómo las variaciones en la frecuencia cardíaca pueden indicar cambios en la actividad autonómica del organismo.

𝙤𝙗𝙟𝙚𝙩𝙞𝙫𝙤

Identificar los cambios en el balance autonómico a partir del análisis temporal de la variabilidad de la frecuencia cardíaca (HRV), aplicando técnicas de procesamiento digital de señales para el filtrado y estudio de los intervalos R-R, y comparando la respuesta cardíaca en condiciones de reposo y durante la lectura en voz alta, con el propósito de relacionar la actividad simpática y parasimpática en ambos estados fisiológicos.

𝙞𝙢𝙥𝙤𝙧𝙩𝙖𝙘𝙞ó𝙣 𝙙𝙚 𝙡𝙞𝙗𝙧𝙚𝙧𝙞𝙖𝙨
<h1 align="center"><i><b>𝐏𝐚𝐫𝐭𝐞 A 𝐝𝐞𝐥 𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐨𝐫𝐢𝐨</b></i></h1>

```python
import matplotlib.pyplot as plt
from matplotlib.patches import FancyBboxPatch, ArrowStyle, FancyArrowPatch
import numpy as np
import os

fig, ax = plt.subplots(figsize=(12,6))
ax.set_xlim(0, 12)
ax.set_ylim(0, 6)
ax.axis('off')

def box(x, y, w, h, text, fontsize=11):
    rect = FancyBboxPatch((x, y), w, h, boxstyle="round,pad=0.3", linewidth=1.5)
    ax.add_patch(rect)
    ax.text(x + w/2, y + h/2, text, ha='center', va='center', fontsize=fontsize, wrap=True)

# Cajas (ajusta textos si lo deseas)
box(0.5, 3.8, 2.2, 1.0, "Investigación\ntheórica\n(Actividad simpática/\nparasimpática, HRV,\nPoincaré)", fontsize=10)
box(3.0, 3.8, 2.2, 1.0, "Plan de acción\n(Diagrama de flujo\nprocedimental)", fontsize=10)
box(5.5, 3.8, 2.2, 1.0, "Adquisición\nECG (4 min)\n— 2 min reposo\n— 2 min lectura", fontsize=10)

box(0.5, 1.8, 2.2, 1.0, "Verificación\nde muestreo y\nniveles de cuantificación", fontsize=10)
box(3.0, 1.8, 2.2, 1.0, "Pre-procesamiento\nFiltrado digital\n(Diseño IIR)", fontsize=10)
box(5.5, 1.8, 2.2, 1.0, "Segmentación\n(2 segmentos\nx 2 min)", fontsize=10)

box(8.0, 3.8, 3.0, 1.0, "Detección de\npicos R\nCálculo de\nintervalos R-R", fontsize=10)
box(8.0, 1.8, 3.0, 1.0, "Análisis HRV\n(Dominio del tiempo:\nmedia RR, SDNN,\nRMSSD, pNN50)\nDiagrama de Poincaré", fontsize=10)

def arrow(x1, y1, x2, y2):
    arr = FancyArrowPatch((x1,y1),(x2,y2), arrowstyle=ArrowStyle("->", head_length=8, head_width=4), mutation_scale=12, linewidth=1.2)
    ax.add_patch(arr)

# Flechas de conexión
arrow(2.7, 4.3, 3.0, 4.3)
arrow(5.2, 4.3, 5.5, 4.3)
arrow(7.7, 4.3, 8.0, 4.3)
arrow(2.7, 2.3, 3.0, 2.3)
arrow(5.2, 2.3, 5.5, 2.3)
arrow(7.7, 2.3, 8.0, 2.3)
arrow(6.6, 3.8, 6.6, 2.8)
arrow(8.9, 2.8, 8.9, 2.0)
arrow(5.8, 2.8, 7.8, 3.6)

ax.text(6.0, 5.6, "Diagrama de bloques — PARTE A (Plan de acción y flujo experimental)", ha='center', fontsize=14, weight='bold')
ax.text(6.0, 5.25, "Diagrama listo para incluir en informe o presentar en GitHub", ha='center', fontsize=10)

out_path = "/mnt/data/diagrama_parteA.png"
plt.tight_layout()
plt.savefig(out_path, dpi=200, bbox_inches='tight')
plt.show()
print(f"Diagrama guardado en: {out_path}")
```

𝙛𝙪𝙣𝙙𝙖𝙢𝙚𝙣𝙩𝙤 𝙩𝙚𝙤𝙧𝙞𝙘𝙤 

En la primera parte de la práctica se realizó una investigación teórica sobre la actividad simpática y parasimpática del sistema nervioso autónomo, su influencia en la frecuencia cardíaca y el concepto de variabilidad de la frecuencia cardíaca (HRV). Además, se estudió cómo la señal electrocardiográfica (ECG) permite obtener los intervalos R-R necesarios para el análisis de la HRV y se revisó el uso del diagrama de Poincaré como herramienta gráfica para evaluar el equilibrio entre la actividad simpática y parasimpáticaEn la primera parte de la práctica se realizó una investigación teórica sobre la actividad simpática y parasimpática del sistema nervioso autónomo, su influencia en la frecuencia cardíaca y el concepto de variabilidad de la frecuencia cardíaca (HRV). Además, se estudió cómo la señal electrocardiográfica (ECG) permite obtener los intervalos R-R necesarios para el análisis de la HRV y se revisó el uso del diagrama de Poincaré como herramienta gráfica para evaluar el equilibrio entre la actividad simpática y parasimpática.

𝟭. 𝘼𝙘𝙩𝙞𝙫𝙞𝙙𝙖𝙙 𝙎𝙞𝙢𝙥𝙖𝙩𝙞𝙘𝙖 𝙮 𝙋𝙖𝙧𝙖𝙨𝙞𝙢𝙥𝙖𝙩𝙞𝙘𝙖 𝙙𝙚𝙡 𝙨𝙞𝙨𝙩𝙚𝙢𝙖 𝙣𝙚𝙧𝙫𝙞𝙤𝙨𝙤 𝙖𝙪𝙩𝙤𝙣𝙤𝙢𝙤:

𝟮. 𝙀𝙛𝙚𝙘𝙩𝙤 𝙙𝙚 𝙡𝙖 𝙖𝙘𝙩𝙞𝙫𝙞𝙙𝙖𝙙 𝙨𝙞𝙢𝙥𝙖𝙩𝙞𝙘𝙖 𝙙𝙚𝙡 𝙨𝙞𝙨𝙩𝙚𝙢𝙖 𝙣𝙚𝙧𝙫𝙞𝙤𝙨𝙤 𝙖𝙪𝙩𝙤𝙣𝙤𝙢𝙤:

𝟯. 𝙫𝙖𝙧𝙞𝙖𝙗𝙞𝙡𝙞𝙙𝙖𝙙 𝙙𝙚 𝙡𝙖 𝙛𝙧𝙚𝙘𝙪𝙚𝙣𝙘𝙞𝙖 𝙘𝙖𝙧𝙙𝙞𝙖𝙘𝙖 (𝙃𝙍𝘾) 𝙤𝙗𝙩𝙚𝙣𝙞𝙙𝙖 𝙖 𝙥𝙖𝙧𝙩𝙞𝙧 𝙙𝙚 𝙡𝙖 𝙨𝙚𝙣̃𝙖𝙡 𝙚𝙡𝙚𝙘𝙩𝙧𝙤𝙘𝙖𝙧𝙙𝙞𝙤𝙜𝙧𝙖𝙛𝙞𝙘𝙖 (𝙀𝘾𝙂).

La variabilidad de la frecuencia cardíaca (HRV) es un indicador fisiológico que mide las fluctuaciones en el intervalo de tiempo entre latidos consecutivos del corazón, conocidos como intervalos RR. Estos valores se obtienen a través de la señal electrocardiográfica (ECG). Este análisis proporciona información valiosa sobre el equilibrio entre las ramas simpática y parasimpática del sistema nervioso autónomo, responsables de regular la actividad cardíaca (Shaffer y Ginsberg, 2017).

Para calcular la HRV, se registra inicialmente la señal ECG y se identifican los complejos QRS, destacando los picos R, que caracterizan cada ciclo cardíaco. A continuación, se mide el tiempo entre dos picos R consecutivos (intervalo RR). Con esta serie de intervalos, se realiza el análisis de su variabilidad utilizando métodos en el dominio del tiempo o en el dominio de la frecuencia (Malik et al., 1996).

En el dominio del tiempo, los parámetros más habituales son la SDNN (desviación estándar de los intervalos RR) y la RMSSD (raíz cuadrada de la media de las diferencias cuadráticas sucesivas), que reflejan respectivamente la variabilidad global y la influencia del tono vagal. En el dominio de la frecuencia, se analizan componentes espectrales como LF (Low Frequency) y HF (High Frequency), que permiten estudiar el balance entre la actividad simpática y parasimpática. El cociente LF/HF se utiliza como indicador del equilibrio autonómico (Task Force, 1996).

La HRV se ha establecido como una herramienta valiosa tanto en entornos clínicos como en investigaciones. Una alta variabilidad suele asociarse con un sistema cardíaco saludable y una buena capacidad de adaptación fisiológica, mientras que una baja variabilidad puede ser señal de estrés, fatiga o disfunción autonómica. Por esta razón, el análisis de HRV a partir de la señal ECG es considerado un método no invasivo y fiable para evaluar la modulación autonómica del corazón (Shaffer y Ginsberg, 2017).

𝟰. 𝘿𝙞𝙖𝙜𝙧𝙖𝙢𝙖 𝙙𝙚 𝙥𝙤𝙞𝙣𝙘𝙖𝙧𝙚 𝙘𝙤𝙢𝙤 𝙝𝙚𝙧𝙧𝙖𝙢𝙞𝙚𝙣𝙩𝙖  𝙙𝙚 𝙖𝙣𝙖𝙡𝙞𝙨𝙞𝙨 𝙙𝙚 𝙡𝙖 𝙎𝙚𝙣̃𝙖𝙡 𝙍-𝙍:



<h1 align="center"><i><b>Bibliografia</b></i></h1>

° Malik, M., et al. (1996). Heart rate variability: Standards of measurement, physiological interpretation, and clinical use. Circulation, 93(5), 1043–1065.

° Shaffer, F., & Ginsberg, J. P. (2017). An overview of heart rate variability metrics and norms. Frontiers in Public Health, 5, 258.

° Task Force of the European Society of Cardiology and the North American Society of Pacing and Electrophysiology. (1996). Heart rate variability: Standards of measurement, physiological interpretation and clinical use. Circulation, 93(5), 1043–1065.
