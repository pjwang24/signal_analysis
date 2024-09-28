import numpy as np
import matplotlib.pyplot as plt
from scipy.fft import fft, fftfreq

A = 0.1
f_lowe = 82
f_a = 110

sampling_rate = 1000
duration = 0.1
t = np.linspace(0, duration, int(sampling_rate * duration), endpoint=False)

signal_lowe = A*np.sin(2 * np.pi * t * f_lowe)
signal_a = A*np.sin(2 * np.pi * t * f_a)

combined_signal = signal_lowe + signal_a

plt.figure(figsize=(10, 4))
plt.plot(t, combined_signal)
plt.title('Amplitude vs Time for Low E and A Strings Vibrating Together')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.show()

N = len(t)  # Number of samples
yf = fft(combined_signal)  # Compute the FFT
xf = fftfreq(N, 1 / sampling_rate)  # Frequency axis

# Plot the frequency-domain representation (power vs frequency)
plt.figure(figsize=(10, 4))
plt.plot(xf[:N//2], np.abs(yf[:N//2]))  # We plot only the positive frequencies
plt.title('Power vs Frequency for Combined Guitar Signal')
plt.xlabel('Frequency [Hz]')
plt.ylabel('Power')
plt.grid(True)
plt.show()

# Fundamental frequency of A string and its harmonics
A = 0.1
f1 = 110  # Fundamental frequency (A string)
f2 = 233.35  # Second harmonic frequency
f3 = 350.02  # Third harmonic frequency
f4 = 466.70  # Fourth harmonic frequency

# Time axis for the signal
sampling_rate = 1000  # Samples per second
duration = 0.1  # Duration of the signal
t = np.linspace(0, 0.1, int(sampling_rate * duration), endpoint=False)

# Generate the sinusoidal signals for the harmonics
signal_f1 = A*np.sin(2 * np.pi * f1 * t)  # Fundamental frequency
signal_f2 = A*np.sin(2 * np.pi * f2 * t)  # Second harmonic
signal_f3 = A*np.sin(2 * np.pi * f3 * t)  # Third harmonic
signal_f4 = A*np.sin(2 * np.pi * f4 * t)  # Fourth harmonic

# Combine all the harmonic signals
combined_harmonics_signal = signal_f1 + signal_f2 + signal_f3 + signal_f4

# Plot the time-domain signal of the combined harmonics
plt.figure(figsize=(10, 4))
plt.plot(t, combined_harmonics_signal)
plt.title('Combined Signal of Fundamental, Second, Third, and Fourth Harmonics (A String)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.show()

res = 1.68 * (10**(-8)) * 5 / ((8 * 10 ** (-4))**2 * np.pi)
res

cur = 10 / res
cur

d_vel = 239.36/((8.49*10**28)*(8*10**-4)**2 * np.pi * 1.6 * 10**-19)
d_vel

# Constants
A = 0.1  # Amplitude in Volts (100mV)
f_lowE = 82  # Frequency of Low E string in Hz
f_A = 110  # Frequency of A string in Hz
time = np.linspace(0, 0.05, 1000)  # Time array (0 to 50ms)

# Waveforms of Low E and A strings
y_lowE = A * np.sin(2 * np.pi * f_lowE * time)
y_A = A * np.sin(2 * np.pi * f_A * time)

# Combined waveform (sum of both signals)
y_combined = y_lowE + y_A

# Plotting amplitude as a function of time (time domain)
plt.figure(figsize=(10, 6))
plt.plot(time, y_combined, label='Combined Signal (Low E + A)')
plt.title('Amplitude as a Function of Time (Low E and A Strings)')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude (V)')
plt.grid(True)
plt.legend()
plt.show()

# Now let's calculate the power in the frequency domain using FFT
n = len(time)  # Number of sample points
yf = np.fft.fft(y_combined)
xf = np.fft.fftfreq(n, time[1] - time[0])

# Only take the positive half of the spectrum
xf = xf[:n // 2]
yf = 2.0 / n * np.abs(yf[:n // 2])

# Plotting power as a function of frequency (frequency domain)
plt.figure(figsize=(10, 6))
plt.plot(xf, yf, label='Frequency Spectrum (Low E + A)')
plt.title('Power as a Function of Frequency (Low E and A Strings)')
plt.xlim(0, 500)
plt.xlabel('Frequency (Hz)')
plt.ylabel('Power')
plt.grid(True)
plt.legend()
plt.show()
