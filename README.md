# SIMULATION-OF-AUTOCORRELATION-AND-PSD-USING-SCILAB-1-T1-C12-EVEN

---

## AIM:
Write a program for Autocorrelation and PSD of signals in SCILAB and verify Wiener-Khinchin relation.

---

## EQUIPMENTS NEEDED:
- Computer with i3 Processor  
- SCI LAB  

---

## THEORY:
The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the Fourier transform of the corresponding autocorrelation function.

---

## ALGORITHM:

1. Load or Define the Signal: Input your time-domain signal  
2. Compute Autocorrelation: Calculate the autocorrelation function  
3. Compute Power Spectral Density (PSD): Estimate PSD using FFT or other methods  
4. Plot Results: Visualize autocorrelation and PSD  

---

## PROCEDURE:
- Refer Algorithms and write code for the experiment  
- Open SCILAB in System  
- Type your code in New Editor  
- Save the file  
- Execute the code  
- If any error, correct it and execute again  
- Verify the generated waveform using Tabulation and Model Waveform  

---

## PROGRAM
```scilab
clc;
clear;
close;

// Parameters
fs = 1000;          // Sampling frequency
t = 0:1/fs:0.65;    // Time vector
fm = 3;             // Signal frequency

// Signal
x = 25 * sin(2 * %pi * fm * t);

// Autocorrelation
Rxx = xcorr(x, x);

// FFT of signal
X = fft(x);
X_mag = abs(X);

// FFT of autocorrelation
Rxx_fft = fft(Rxx);
Rxx_mag = abs(Rxx_fft);

// Power Spectrum
Pxx = (abs(X).^2) / length(X);

// Plotting
subplot(3,2,1);
plot(t, x);
xtitle("Signal x(t)");
xgrid();

subplot(3,2,2);
plot(Rxx);
xtitle("Autocorrelation");
xgrid();

subplot(3,2,3);
plot(Rxx_mag);
xtitle("FFT of Autocorrelation");
xgrid();

subplot(3,2,4);
plot(X_mag);
xtitle("FFT of Signal");
xgrid();

subplot(3,2,5);
plot(Pxx);
xtitle("Power Spectrum");
xgrid();
```

---

## OUTPUT:
<img width="1919" height="1199" src="https://github.com/user-attachments/assets/ddbb488d-bb20-4f6b-bdfc-8d93c7d5e266" />
<img width="1280" height="652" alt="image" src="https://github.com/user-attachments/assets/18f8b64a-d01c-4ad6-9e48-060d2bcb8107" />


---

## RESULT:
Thus the autocorrelation and power spectral density of the given signal were obtained using SCILAB and the Wiener-Khinchin theorem was verified successfully.
