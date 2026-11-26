# Free-Space Optical Communication (FSO) Implementation

## Aim: 
To implement and analyze a free space optical communication link using a laser/LED transmitter and photodiode/APD receiver.

## Apparatus/Software Required:
Python Colab

## Theory:
	FSO uses light beams to transmit data through free space instead of fiber.
	Performance depends on distance, alignment, and atmospheric attenuation.
	Received power decreases exponentially with distance.

## Formula:
Loss=10⋅〖log⁡〗_10 (P_in/P_out )

## 1
## Setup the Transmitter
Info
Prepare the optical source for transmission.
	Use a Laser/LED source
	Mount it on an optical bench
	Ensure stable power supply

## 2
## Align the Optical Path
Warning
Proper alignment ensures maximum received signal.
	Place transmitter and receiver in line of sight
	Adjust using lenses/mirrors if needed
	Minimize beam divergence

## 3
## Connect the Receiver
Setup the photodiode/APD to detect the optical signal.
	Mount detector opposite to transmitter
	Connect to oscilloscope for signal observation
	Record received power

## 4
## Measure Received Power
Collect data at different distances.
Loss = 10 log10(Pin / Pout)
	Vary distance (1 m, 5 m, 10 m, etc.)
	Note received power in µW
	Calculate link loss

## 5
## Plot Graphs
Visualize performance of FSO link.
	Plot Received Power vs Distance
	Observe exponential decay trend
	Compare with theoretical model

## 6
## Conclude Results
Success
Summarize findings of the experiment.
	Reliable communication up to ~10 m indoors
	Loss increases with distance
	Alignment critical for performance

## Sample Output
Graph: Received Power vs Distance (decay curve)
<img width="630" height="467" alt="image" src="https://github.com/user-attachments/assets/0ec8bb24-ddfb-4d3a-b0f2-a5b661798ad4" />
<img width="672" height="466" alt="image" src="https://github.com/user-attachments/assets/2a113e54-2433-4072-ba62-16539939e93a" />
<img width="672" height="461" alt="image" src="https://github.com/user-attachments/assets/448e0d3f-a834-4e14-953f-4d429b7a9996" />

## Python Code
```
import numpy as np
import matplotlib.pyplot as plt

# --------------------------------
# 1. FSO Attenuation vs Visibility
# --------------------------------
visibility = np.linspace(0.1, 20, 100)

# Simple attenuation model
attenuation = 20 / visibility

plt.figure()
plt.plot(visibility, attenuation)
plt.xlabel("Visibility (km)")
plt.ylabel("Atmospheric Attenuation (dB)")
plt.title("FSO Attenuation vs Visibility (Kruse Model)")
plt.grid()
plt.show()


# --------------------------------
# 2. Rain Attenuation
# --------------------------------
rain = np.linspace(0, 50, 100)

# Simple rain attenuation model
rain_loss = 2 * np.sqrt(rain)

plt.figure()
plt.plot(rain, rain_loss)
plt.xlabel("Rain Rate (mm/hr)")
plt.ylabel("Rain Attenuation (dB/km)")
plt.title("Rain Attenuation in FSO Link")
plt.grid()
plt.show()


# --------------------------------
# 3. Attenuation vs Wavelength
# --------------------------------
wavelength = np.linspace(800, 1600, 100)

# Simple fog attenuation model
fog_loss = 20 * (800 / wavelength) ** 2

plt.figure()
plt.plot(wavelength, fog_loss)
plt.xlabel("Wavelength (nm)")
plt.ylabel("Attenuation (dB)")
plt.title("Attenuation vs Wavelength (Fog Condition)")
plt.grid()
plt.show()


# --------------------------------
# Result
# --------------------------------
print("Result:")
print("Reliable FSO link up to ~10 m indoors;")
print("beyond that, signal quality degrades significantly.")
```

## Output
 <img width="437" height="572" alt="image" src="https://github.com/user-attachments/assets/2d969fb7-711b-43e7-9b4e-fc05746cd014" />

<img width="541" height="320" alt="image" src="https://github.com/user-attachments/assets/3a2fc9dc-065d-46e2-95e7-251d6b549416" />

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/f2358c07-fc50-4632-b00e-80dd16f9d4a2" />

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/1a8f85a7-c778-48dc-ab60-f98cf9af2393" />

  
## Result

Reliable FSO link up to ~10 m indoors; beyond that, signal quality degrades significantly. 
