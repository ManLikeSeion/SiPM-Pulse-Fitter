# SiPM-Pulse-Fitter
This repository contains a Jupyter Notebook designed for Silicon Photomultiplier (SiPM) single event modelling. It simulates realistic SiPM pulse signals, including noise and dark counts, and subsequently analyses the generated events using matched filtering and curve fitting.

# Workflow
Initial Pulse Creation: Generates a baseline pulse that always begins 50 ns after the start of the event.  Dark Count Simulation: Uses a defined dark count rate to randomly determine the number of additional pulses via a Poisson distribution.  Additional Pulses: Injects these extra pulses with random amplitudes (in discrete scale units) and random temporal positions based on an exponential distribution.  Signal Filtering: Analyses the event by filtering the raw data with a normalised matched filter template.  Peak Finding & Fitting: Locates peaks in the filtered response and uses these positions as initial parameters to fit all peaks, effectively resolving overlapping signals.  Visualisation: Plots the generated raw noisy data alongside the final fitted curve for verification.  
# Dependencies
To run the notebook, the following Python libraries are required:  numpy  scipy (specifically scipy.signal.find_peaks and scipy.optimize.curve_fit)  matplotlib  random (standard library)  
# Technical Details
The modelling operates on a nanosecond (ns) timescale, evaluating amplitude in millivolts (mV) to mimic realistic hardware outputs. The default configuration features a 2.0 ns rise time, a 150.0 ns decay time, and an equivalent dark count rate of 2 MHz.  

#Results
An example fit
<img width="640" height="480" alt="SiPM pulse" src="https://github.com/user-attachments/assets/aa74102a-5e67-42b0-90a3-592bce5e3b0a" />
