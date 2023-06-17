# Proyecto-ICH1104 Grupo 13

# Apuntes Ayudantía proyecto:

```vel = np.linalg.norm([u_prom, v_prom], axis=0)``` donde ```u_prom = mean_u_t = u_array.mean(axis=(0,1))``` y ```v_prom = mean_v_t = v_array.mean(axis=(0,1))```. Esta velocidad se usará para la transformada de Fourier.

# Transofrmada de Fourier
Es necesario que sea en 1D (en un punto en el espacio, no sirve matricialmente). Usar la velocidad total (```vel```)
La amplitud sería la energía del espectro

Tamaño del vórtice característico: ```l = np.arrange(0, np.floor(N/2), dtype = "int")``` donde ```N = len(vel)```. También crean la variable ```f = vel``` (una copia de la velocidad, para no cambiar los resultados obtenidos anteriormente)
$t = \frac{l'}{u'}$: Tiempo característico = longitud característica / Velocidad característica
$k = \frac{2\pi}{l'}$: Longitud de onda característica
$\frac{2\pi}{\eta}$: Longitud de onda de los esfuerzos viscosos ($\eta$: Escalas de Kolmogorov)

```np.correlate(u_prom, v_prom, "full")``` Calcular la autocorrelación (En la ayudantía lo pusieron con las velocidades promedio, averiguar si realmente es así o no, porque debiese ser con las prima)

Forma matricial: Encontrar TKE promedio (en todo el tiempo) en cada punto y hacer un mapa de calor (averiguar sobre mapas de calor en matplotlib)
Forma 1D: En cada instante de tiempo, calcular el TKE y graficarlo (energía vs tiempo)
(Esto mismo puede servir para poder graficar las velocidades)

Eliminación de outliers (Lo de eliminar los datos erróneos): Alguien mencionó algo sobre el IQR y la minería de datos y un 1.5. Hay que buscar una cita, independientemente de lo efectiva que sea muy buena o no. Es algo relacionado con Machine Learning.


Cálculo de vorticidad:

$$\omega_{z} = \frac{\partial v}{\partial x} - \frac{\partial u}{\partial y}$$ No saben como calcularlo ajajaaja
