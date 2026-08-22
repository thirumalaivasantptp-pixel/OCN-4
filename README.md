# Wavelength Division Multiplexing (WDM) Simulation

## Aim 
To simulate a WDM system using Python and analyze channel separation and insertion loss.

## Apparatus/Software Required
	Python (NumPy)
	Google Colab or Jupyter Notebook

## Theory
	WDM allows multiple optical signals at different wavelengths to be transmitted simultaneously over a single fiber.
	Channel spacing determines spectral efficiency and crosstalk.
	Insertion loss is the reduction in signal power due to multiplexing/demultiplexing.

## Formula:
"Insertion Loss (dB)"=P_in-P_out
"Channel Spacing"=Δλ

## 1
## Setup Environment
Info
Prepare Python environment for simulation.
	Import NumPy and Matplotlib
	Define channel wavelengths and powers

## 2
## Define WDM Parameters
Specify input wavelengths and powers.
Example: λ = [1550, 1552, 1554] nm, Pin = -2 dBm
	Choose 3 channels
	Assign equal input power

## 3
## Calculate Output Power
Simulate insertion loss for each channel.
Insertion Loss = Pin - Pout
	Assume ~1 dB loss per channel
	Compute Pout

## 4
## Plot WDM Spectrum
Visualize channel separation.
	Use Matplotlib to plot wavelength vs power
	Label each channel peak

## 5
## Analyze Results
Success
Interpret the simulation output.
	Channels separated with ~1–2 dB insertion loss
	Verify spacing Δλ = 2 nm

## Sample Output
 <img width="623" height="478" alt="image" src="https://github.com/user-attachments/assets/7569e8ec-3417-4669-b37b-06029f87655a" />

 <img width="677" height="466" alt="image" src="https://github.com/user-attachments/assets/e937804f-b55d-4de9-ab1e-155e6bd01d8e" />

 <img width="652" height="456" alt="image" src="https://github.com/user-attachments/assets/d22a7a99-0cd4-439e-b49b-b9dde93ab78b" />

## Python Code 


## Sample Output


## Result 

