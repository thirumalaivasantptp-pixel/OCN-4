# Wavelength Division Multiplexing (WDM) Simulation

## Aim

To simulate a WDM system using Python and analyze channel separation and insertion loss.

## Apparatus/Software Required

* Python (NumPy)
* Google Colab or Jupyter Notebook

## Theory

WDM allows multiple optical signals at different wavelengths to be transmitted simultaneously over a single fiber.
Channel spacing determines spectral efficiency and crosstalk.
Insertion loss is the reduction in signal power due to multiplexing/demultiplexing.

## Formula:

**Insertion Loss (dB) = P_in − P_out**

**Channel Spacing = Δλ**

## 1

## Setup Environment

Prepare the Python environment for simulation.

* Import NumPy and Matplotlib.
* Define the channel wavelengths and input powers.

## 2

## Define WDM Parameters

Specify the input wavelengths and powers.

* Choose 3 optical channels.
* Set the channel wavelengths as 1550 nm, 1552 nm, and 1554 nm.
* Assign equal input power of −2 dBm to each channel.
* The channel spacing is selected as 2 nm.

## 3

## Calculate Output Power

Simulate insertion loss for each channel.

* Assume an insertion loss of approximately 1 dB per channel.
* Calculate the output power using:

**P_out = P_in − Insertion Loss**

For an input power of −2 dBm and an insertion loss of 1 dB:

**P_out = −2 − 1 = −3 dBm**

## 4

## Plot WDM Spectrum

Visualize the separation between the WDM channels.

* Create a wavelength range around the selected channel wavelengths.
* Plot the power level of each channel using Matplotlib.
* Represent each channel as a peak at its corresponding wavelength.
* Label the channel peaks and wavelength values.
* Display the input and output power levels for comparison.

## 5

## Analyze Results

Interpret the simulation output.

* The three WDM channels are clearly separated in the spectrum.
* The wavelengths are 1550 nm, 1552 nm, and 1554 nm.
* The channel spacing is verified as **Δλ = 2 nm**.
* With an assumed insertion loss of 1 dB, the output power of each channel is **−3 dBm**.
* The simulation demonstrates that multiple optical channels can be transmitted over a single fiber using different wavelengths.

## Sample Output

The following output is obtained from the simulation:

```text
WDM Channel Parameters
----------------------
Channel 1: λ = 1550 nm, Pin = -2 dBm, Pout = -3 dBm
Channel 2: λ = 1552 nm, Pin = -2 dBm, Pout = -3 dBm
Channel 3: λ = 1554 nm, Pin = -2 dBm, Pout = -3 dBm

Channel Spacing:
Δλ = 2 nm

Insertion Loss:
1 dB per channel
```

The plotted WDM spectrum shows three distinct peaks corresponding to the wavelengths **1550 nm, 1552 nm, and 1554 nm**. Each channel experiences an insertion loss of approximately **1 dB**.

## Python Code

```python
import numpy as np
import matplotlib.pyplot as plt

# WDM channel parameters
wavelengths = np.array([1550, 1552, 1554])  # nm
Pin = np.array([-2, -2, -2])                # dBm

# Assumed insertion loss
insertion_loss = np.array([1, 1, 1])        # dB

# Calculate output power
Pout = Pin - insertion_loss

# Calculate channel spacing
channel_spacing = np.diff(wavelengths)

# Display results
print("WDM Channel Parameters")
print("----------------------")

for i in range(len(wavelengths)):
    print(f"Channel {i+1}: λ = {wavelengths[i]} nm, "
          f"Pin = {Pin[i]} dBm, Pout = {Pout[i]} dBm")

print("\nChannel Spacing:")
print("Δλ =", channel_spacing, "nm")

print("\nInsertion Loss:")
print(insertion_loss, "dB per channel")

# Create spectrum for plotting
wavelength_range = np.linspace(1548, 1556, 1000)
spectrum = np.full_like(wavelength_range, -20.0)

# Generate Gaussian-shaped channel peaks
for wavelength, power in zip(wavelengths, Pout):
    spectrum += (power + 20) * np.exp(
        -((wavelength_range - wavelength) ** 2) / (2 * 0.08 ** 2)
    )

# Plot WDM spectrum
plt.figure(figsize=(8, 5))
plt.plot(wavelength_range, spectrum, label="WDM Spectrum")

# Mark channel wavelengths
plt.scatter(wavelengths, Pout, zorder=3)

for wavelength, power in zip(wavelengths, Pout):
    plt.annotate(
        f"{wavelength} nm",
        (wavelength, power),
        xytext=(0, 10),
        textcoords="offset points",
        ha="center"
    )

plt.xlabel("Wavelength (nm)")
plt.ylabel("Power (dBm)")
plt.title("Wavelength Division Multiplexing (WDM) Spectrum")
plt.grid(True)
plt.legend()
plt.show()
```

## Sample Output

<img width="623" height="478" alt="image" src="https://github.com/user-attachments/assets/7569e8ec-3417-4669-b37b-06029f87655a" />

<img width="677" height="466" alt="image" src="https://github.com/user-attachments/assets/e937804f-b55d-4de9-ab1e-155e6bd01d8e" />

<img width="652" height="456" alt="image" src="https://github.com/user-attachments/assets/d22a7a99-0cd4-439e-b49b-b9dde93ab78b" />

The simulation produces a spectrum containing three distinct optical channel peaks at **1550 nm, 1552 nm, and 1554 nm**. The output power of each channel is approximately **−3 dBm**, corresponding to an insertion loss of **1 dB** from the input power of −2 dBm.

The wavelength difference between adjacent channels is **2 nm**, confirming the specified channel spacing.

## Result

The WDM system was successfully simulated using Python. Three optical channels at **1550 nm, 1552 nm, and 1554 nm** were multiplexed with a channel spacing of **2 nm**. An insertion loss of **1 dB per channel** resulted in an output power of **−3 dBm** for each channel. The plotted spectrum clearly shows the separation of the three WDM channels.
