# Laboratorio-5-Frecuencia-cardiaca-HRV
𝙞𝙣𝙩𝙧𝙤𝙙𝙪𝙘𝙘𝙞ó𝙣

La variabilidad frecuenciaacardíacadíaca (HRV) es un parámetro fisiológico que permite evaluar el equilibrio entre las ramas simpática y parasimpádela del sistema nervioso autónomo a través del análisis de los intervalos R-R obtenidos de la señal electrocardiográfica (ECG). Este parámetro es una herramienta fundamental en el estudio de la regulación cardíaca, ya que refleja la capacidad del corazón para adaptarse a diferentes estados fisiológicos, como el reposo o la actividad mental. En esta práctica se analizó la HRV mediante técnicaorganismodigital de señales, utilizando herramientas computacionales como Python para el filtrado, segmentación y análisis de los datos, con el fin de comprender cómo las variaciones en la frecuencia cardíaca pueden indicar cambios en la actividad autonómica del organismo.

𝙤𝙗𝙟𝙚𝙩𝙞𝙫𝙤

Identificar los cambios en el balance autonómico a partir del análisis temporal de la variabilidad de la frecuencia cardíaca (HRV), aplicando técnicas de procesamiento digital de señales para el filtrado y estudio de los intervalos R-R, y comparando la respuesta cardíaca en condiciones de reposo y durante la lectura en voz alta, con el propósito de relacionar la actividad simpática y parasimpática en ambos estados fisiológicos.

𝙞𝙢𝙥𝙤𝙧𝙩𝙖𝙘𝙞ó𝙣 𝙙𝙚 𝙡𝙞𝙗𝙧𝙚𝙧𝙞𝙖𝙨
<h1 align="center"><i><b>𝐏𝐚𝐫𝐭𝐞 A 𝐝𝐞𝐥 𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐨𝐫𝐢𝐨</b></i></h1>

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
