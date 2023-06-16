# Proyecto-ICH1104 Grupo 13
Integrantes:
1) Fernando Bittelman
2) Alonso Espinoza
3) Sebastián Fuenzalida
4) Fernanda Joustra


Apuntes Ayudantía proyecto:

Averiguar sobre el transpose y el reshape
u = np.transpose(u.reshape(medidas), (coordenadas)) # Creo que esto puede servir para obtener valores promediados en un tiempo y no en un punto, en la ayudantía pusieron esto

Agregan axis=2 (matriz) en el np.mean (np.mean(u, axis=2)) # Con esto se tiene un resultado matricial (velocidad en todo el espacio)
(np.mean(u, axis=(0,1))) # Con esto se obtiene un resultado puntual, esto será útil para graficar la velocidad en un punto

vel = np.linalg.norm([u_prom, v_prom], axis=0)

Transformada de Fourier:
Es necesario que sea en 1D (en un punto en el espacio, no sirve matricialmente). Usar la velocidad total
La amplitud sería la energía del espectro

Tamaño del vórtice característico: l = np.arrange(0, np.floor(N/2), dtype = "int")
t = l'/u' : longitud característica / velocidad característico
k = 2π/l' longitud de onda característica
2π/n: Tamaño característico de los esfuerzos viscosos (n: Escalas de Kolmogorov)

np.correlate(u_prom, v_prom, "full") -> Calcular la autocorrelación

Forma matricial: Encontrar TKE promedio (en todo el tiempo) en cada punto y hacer un mapa de calor (averiguar sobre mapas de calor en matplotlib)
Forma 1D: En cada instante de tiempo, calcular el TKE y graficarlo (energía vs tiempo)
(Esto mismo puede servir para poder graficar las velocidades)

Eliminación de outlayers (Lo de eliminar los datos erróneos): Alguien mencionó algo sobre el IQR y la minería de datos y un 1.5. Hay que buscar una cita, independientemente de lo efectiva que sea muy buena o no.


Cálculo de vorticidad:

$$\omega_{z} = \frac{\partial v}{\partial x} - \frac{\partial u}{\partial y}$$. No saben como calcularlo ajajaaja
