## Colamarino Luca 1944447, Leo Emilio 1966813
# Echolocation-using-wifi-sensors
Project on Echolocation using wifi.sensors, to guide blind people to find positions in the space

Datasets:
- Widar 3.0
- UT-HAR
-

objective:
transform the problem in a image classification problem to use the power of 2d-Cnn.

Steps:

- PCA to extract the main components
- STFT on main component of CSI to obtain the spectrogram
- Generate Image:
    x: time
    y: frequency
    intensity: power of the signal
(sx,dx <- fast change in the sign of the frequency or dispersion of energy on more frequencies)

out dataset will be composed as follow:
-0: Forward ->  2sec window extracted from UT-HAR "Walking"
-1: Stop ->  2sec window extracted from UT-HAR "Standing"
-2: Right ->  complete campion from widar3.0 (right gesture)
-3: Left ->  complete campion from widar3.0 (left gesture)

merging sweep and slide (left and right)may  make the model more robust

to reduce computational cost we can use dwt wich is lighter
