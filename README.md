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

La variación en el tiempo entre dos latidos del corazón se denomina VFC. Es uno de los indicadores de muchas condiciones patológicas relacionadas con la salud cardiovascular. Proporcionó información confiable sobre la interacción de los sistemas nerviosos simpático y parasimpático. El análisis de la variación de la frecuencia cardíaca es una técnica no invasiva bien conocida para identificar el funcionamiento del sistema nervioso autónomo. El sistema nervioso autónomo (SNA) depende del sistema nervioso simpático y parasimpático para transferir información. El centro cardioacelerador, los pulmones y los músculos no estriados están inervados por nervios simpáticos cardíacos. Esta división del ANS se aferra al corazón en consecuencia viael ganglio cervicotorácico y el nervio vago. Se encuentra que la variabilidad normal cardíaca depende de esta estimulación hacia el nódulo sinoauricular (marcapasos), la cual puede evaluarse analizando la VFC. En estudios realizados en humanos, se ha descubierto que un nivel bajo de VFC es una de las principales causas de muerte entre los adultos. Por tanto, la VFC ayuda a identificar el riesgo de enfermedades cardíacas y el estado del SNA.

𝟰. 𝘿𝙞𝙖𝙜𝙧𝙖𝙢𝙖 𝙙𝙚 𝙥𝙤𝙞𝙣𝙘𝙖𝙧𝙚 𝙘𝙤𝙢𝙤 𝙝𝙚𝙧𝙧𝙖𝙢𝙞𝙚𝙣𝙩𝙖  𝙙𝙚 𝙖𝙣𝙖𝙡𝙞𝙨𝙞𝙨 𝙙𝙚 𝙡𝙖 𝙎𝙚𝙣̃𝙖𝙡 𝙍-𝙍:


