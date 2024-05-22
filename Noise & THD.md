# Total Harmonic Distortion THD

If everything works well, then your speaker THD curve will show nothing too abnormal and be at a low level. A good THD level to aim for as a speaker engineer is a distortion level of at least -40dB from your fundamental frequency, which equates to a distortion level of 1%.

As an audiophile, if you are concerned about THD and comparing speakers, then the lower the THD value the better.

**Second-order** or ‘even’ harmonics are even-numbered multiples of the fundamental frequencies and create a rich, pleasing sound. 

**Third-order** or ‘odd’ harmonics are odd-numbered multiples of the fundamental frequencies, which give the signal an edgier, more aggressive sound.

THD+N = Total Harmonic Distortion + Noise

# SINAD


$$ SINAD = 20 * \log{\frac{1}{THD+N}}$$
- >120dB (>20 bits): Provably inaudible noise and distortion.
- 109dB—119dB (18 bits—20 bits): Well beyond 16-bit (CD) resolution.
- 96dB—108dB (16 bits—18 bits): Meets and exceeds 16-bit (CD) resolution.
- 85dB—95dB (14.3 bits—16 bits): Does not meet 16-bit (CD) resolution.
- <85dB (<14.3 bits): Performance is below the minimum lenient threshold defined in [this thread.](https://www.audiosciencereview.com/forum/index.php?threads/audibility-thresholds-of-amp-and-dac-measurements.5734/)

THD+N 
<0.0001% Great
0.0001% - 0.0004%  Well beyond 16-bit (CD) resolution
0.0004% - 0.0015%  Meets and exceeds 16-bit (CD) resolution
0.0015% - 0.0056%  Does not meet 16-bit (CD) resolution
\> 0.0056% Bad


# Thresholds
## Lenient
Dynamic range, linearity: 96 dB  
THD, IMD (intermodulation distortion): -66 dBFS / 0.05%  
Noise: -85 dBFS / 0.005%  
SINAD: 85 dB  
Crosstalk: -60 dBFS  
Jitter: -110 dBFS, -100 dBFS around the main tone  
Frequency response: ±0.5 dB  
Channel balance: 1 dB  
Output impedance: 2 ohms  
  
## Strict
Dynamic range, linearity, SINAD: 120 dB  
THD, IMD, noise, crosstalk, jitter: -120 dBFS / 0.0001%  
Frequency response, channel balance: ±0.1 dB  
Output impedance: 0.16 ohms

