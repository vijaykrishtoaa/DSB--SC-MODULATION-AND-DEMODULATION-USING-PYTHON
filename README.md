# DSB--SC-MODULATION-AND-DEMODULATION-USING-PYTHON

__AIM__:

To generate a Double Sideband Suppressed Carrier (DSB-SC) signal in Python (Google Colab), transmit it (optionally add noise), and recover the message using coherent (synchronous) demodulation with a low-pass filter. Observe time and frequency domain waveforms and measure demodulation performance

__APPARATUS REQUIRED__:

Google Colab (or any Python environment)

Python libraries: numpy, matplotlib, scipy (scipy.signal)

__Theory__:

DSB-SC signal: s(t) = m(t) · cos(2πf_c t)
Coherent demodulation: multiply received s(t) by a synchronized carrier cos(2πf_c t) then low-pass filter (LPF) to remove double-frequency components:

r(t) = s(t)·cos(2πf_c t) = m(t)·cos²(2πf_c t) = 0.5 m(t) + 0.5 m(t)·cos(4πf_c t)
LPF extracts 0.5·m(t) → scale by 2 to recover m(t).

__Procedure__:

1) Import libraries and set parameters
2) Define message and carrier signals
3) Generate DSB-SC signal (modulation)
4) View spectra (FFT) of message and DSB-SC
5) (Optional) Add noise
6) Coherent demodulation (multiply by synchronized carrier)
7) Low-pass filter to recover message

   __Tabulation__:
![WhatsApp Image 2025-11-26 at 19 54 31_c505ccc0](https://github.com/user-attachments/assets/93a66414-40d7-4faf-9049-5c04d327bba0)
![WhatsApp Image 2025-11-26 at 19 54 30_a3407294](https://github.com/user-attachments/assets/3d874c5d-e2f1-4713-a354-029a3cde944a)
Program:

import numpy as np
import matplotlib.pyplot as plt
Am = 6
fm = 476
Ac = 12
fc = 4760
fs = 47600
b = 6.1
t=np.arange(0, /fm, 1/fs)
m = Am*np.cos(2*3.14*fm*t)
plt.subplot(3,1,1)
plt.plot(t,m)
c= Ac*np.cos(2*3.14*fc*t)
plt.subplot(3,1,2)
plt.plot(t,c)
s=Ac*np.cos(2*3.14*fc*t+b*np.sin(2*3.14*fm*t))
plt.subplot(3,1,3)
plt.plot(t,s)



   __Output__:
![WhatsApp Image 2025-11-26 at 19 44 47_211dc51d](https://github.com/user-attachments/assets/94d6604b-a741-4447-97ce-ffa7aedeb198)

   __Result__:
the message,carrier and amplitude modulation signal will be displayed in separate plots using python.
