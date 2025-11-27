# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.
__PROGRAM__:
```import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

# Given values
Am = 2.24
Fm = 12
Ac = 5.6
Fc = 24
Fs = 240

t = np.arange(0, 2/Fm, 1/Fs)

# Message signal
em = Am * np.sin(2 * np.pi * Fm * t)

# Carrier signal
ec = Ac * np.sin(2 * np.pi * Fc * t)

# AM Modulated signal
eam = (Ac + Am * np.sin(2 * np.pi * Fm * t)) * np.sin(2 * np.pi * Fc * t)

# Demodulated signal using Hilbert transform
demodulated_signal = np.abs(hilbert(eam)) - Ac

# Plotting
plt.figure(figsize=(10, 10))

plt.subplot(4, 1, 1)
plt.plot(t, em)
plt.title("Message Signal")
plt.grid(True)

plt.subplot(4, 1, 2)
plt.plot(t, ec)
plt.title("Carrier Signal")
plt.grid(True)

plt.subplot(4, 1, 3)
plt.plot(t, eam)
plt.title("AM Modulated Signal")
plt.grid(True)

plt.subplot(4, 1, 4)
plt.plot(t, demodulated_signal)
plt.title("Demodulated Signal")
plt.grid(True)

plt.tight_layout()
plt.show()
```
__TABULATION__:
<img width="608" height="693" alt="Screenshot 2025-11-11 102814" src="https://github.com/user-attachments/assets/78da1456-4e1c-4383-9895-7d47ac1bbbbf" />


 __Output__:

<img width="1182" height="943" alt="Screenshot 2025-11-17 195752" src="https://github.com/user-attachments/assets/88d4f2ee-788f-480a-b142-aee839edd318" />

 __Result__:

Thus the amplitude modulation using the python with the colab software is verified successfully.
