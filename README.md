# Quadrature-Down-Converter

Below figure depicts a quadrature down converter (QDC) that is commonly used in modern day wireless receivers (RX) such as Bluetooth, Wi-Fi and WLAN. Quadrature downconversion helps in interference
mitigation and improves the quality of communication. In this project, we will implement a prototype
of QDC for given specifications.

![image](https://user-images.githubusercontent.com/101704193/233806583-e3b13ac3-be51-47fa-bcf0-c3e43809cd4b.png)

As shown in Fig. 1, the input signal vin = A1 cosωint is mixed with vOSCI = A2 cosωOSCt
and vOSCQ = A2 sinωOSCt to produce in-phase (vIFI
) and quadrature-phase (vIF Q
) intermediate frequency (IF) signals, respectively. The in-phase and quadrature-phase signals have a phase difference
of 90°. Mixing of two signals is equivalent to their multiplication as shown below.
vIFI = vin × vOSCI =
A1A2
2

cos(ωint − ωOSCt) + cos(ωint + ωOSCt)

vIF Q = vin × vOSCQ =
A1A2
2

sin(ωint + ωOSCt) − sin(ωint − ωOSCt)

As shown in Fig. 1, the mixed signal is fed a low pass filter to pass only the IF signals with
frequency ωIF = (ωIN − ωOSC), which can be sufficiently low value for sufficiently high values of
ωIN and ωosc. For example, if fIN = 2.4 GHz and fosc = 2.401 GHz, then fIF = 1 MHz

## Quadrature oscillator design
Using opamps, we have designed a quadrature oscillator which produces two sinusoidal signals (vOSCI& vOSCQ
)
at 100 kHz with a phase difference of 90°and oscillation amplitude of 1 Vp−p.
- Clearly shown the topology, calculations for finding component (VDD/VSS/R/C/L/W/L (as
applicable)) values and schematic with annotated component values.
- Given plots for vOSCI& vOSCQ
from transient simulation and FFT. Clearly marked the phase difference between two signals
on transient plots.
- Realized the circuit in lab by using 741 opamp IC and other passive components. From
the measurements, reported the transient waveforms and FFT spectrum for the two signals.
(Suggested references: [1] Chapter 2 and 14 from ‘Microelectronic Circuits’ (7
th edition) by
Sedra and Smith. [2] Ron Mancini, “Design of op amp sine wave oscillators”, Texas Instrument, 2000. [3] Ralph Holzel, “A Simple Wide-Band Sine Wave Quadrature Oscillator”, IEEE
TRANSACTIONS ON INSTRUMENTATION AND MEASUREMENT, VOL. 42, NO. 3, JUNE
1993.)

## Switch (mixer) design
As shown in Fig. 2, a simple MOSFET can be used as a switch (mixer), where the oscillator
signal is applied to the gate of the device, input is applied at the source and the intermediate
frequency output is taken at the drain end.

![image](https://user-images.githubusercontent.com/101704193/233806703-ae996460-b982-4fdb-b412-79e72ba6f24f.png)


- As shown in Fig. 2, implemented the mixer using an NMOS in LTSpice. Clearly mentioned
the values of RBIAS, CC. Consider RL = 1 kΩ, amplitude of vin is 100 mV and frequency
is fIN . Shown transient plots of vin, vIF for fIN = {95, 98 kHz, 99 kHz, 101 kHz, 102,
105 kHz}. Also shown corresponding FFT plots for vIF .
- Realized the circuit in lab using the NMOS transistors and reported above component values
and plots from measurements.

## Low pass filter design
- Designed a low pass RC filter (LPF) with -3 dB cut off frequency of 2 kHz. 
- Reported frequency response (output magnitude vs frequency) from AC analysis in LTSpice
simulations.
- Reported transient response for 1 kHz signal and 10 kHz using LTSpice simulations.
- Realized the circuit in lab and report AC and transient plots from measurements.
- Connected mixer setup in previous part and LPF and reported results from simulations and
measurements.

## Complete circuit prototype design
Connected all building blocks (oscillator, mixer, filter) and made the complete circuit shown in
Fig. 1. Clearly shown and tabulated all component/supply values in the schematic.
- Ran transient simulations and clearly shown waveforms (input, oscillator, IF, IF (FINAL)).
Clearly annotated to show the phase difference between the I-Q components.
- Reported FFT plots of IF (FINAL- I and Q both).
- Realized the complete circuit in lab and reported transient plots of vIN , vOSCI
, vOSCQ
, vIFI
,
vIF Q
, vIF FINALI
and vIF FINALQ
from measurements. Clearly shown the corresponding
phase difference in the I-Q plots for every result.
- Reported FFT plots of vIF FINALI
and vIF FINALQ
from measurements.

## Project report
Made a comprehensive project report in IEEE two column format.
