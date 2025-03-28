# Exp:1 Ideal Sampling
# Name: Dharshini V S
# Reg. No.: 212223060050

### Aim:

To demonstrate ideal sampling of a continuous signal using Scilab, ensuring accurate signal reconstruction while avoiding aliasing.

### Tools required:
Python IDE 

### Program:
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```

### output:
![image](https://github.com/user-attachments/assets/232d5ecb-b4b0-451c-b530-d2c31aa34a5c)

![image](https://github.com/user-attachments/assets/e819626c-b1d0-47ed-8444-f1a460a538cd)

![WhatsApp Image 2025-03-28 at 10 41 31_39a9df14](https://github.com/user-attachments/assets/736ac954-e571-4119-9f7f-5680c0dff9bc)

### Result:
Ideal sampling captures a continuous signal at perfect intervals, ensuring accurate reconstruction if sampled at twice the highest frequency (Nyquist rate). It’s a key concept in digital signal processing and telecommunications. Practical systems approximate ideal sampling with some limitations.


