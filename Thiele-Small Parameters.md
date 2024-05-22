
Or T/S Parameters

# F

$F_s$ - driver resonance frequency
any speaker will have a hard time to play any frequency below the $F_s$

$$
f_s = \frac{1}{2\pi\sqrt{C_{ms} \cdot M_{ms}}}
$$

$F_0$ - The frequency when frequency response start to drop
$F_3$ - frequency where the 3 decibel power drop occurs, less than this you will feel that the sound is quieter
$F_b$ - box resonance frequency

# Q

**Q** - Quantity factor, the magnification of resonance factor of any resonant device or circuit. A driver with a high Q is more resonant than one with a low Q.  

**Q** can also be called as "damping" lower Q will have more damping (more damping is more clear more good things)

$Q_{ms}$ - the mechanical Q of the driver.  (Spring from surround and spider)
- Higher $Q_{ms}$ drivers displaying a higher impedance peak

$Q_{es}$ - the electrical Q of the driver.  This causes by Back EMF (same as motor)
  
$Q_{ts}$ - the total Q of the driver at Fs. 

$$ \frac{1}{Q_{ts}} = \frac{1}{Q_{ms}} + \frac{1}{Q_{es}}$$

$$Q_{ts} = \dfrac{Q_{es} \cdot Q_{ms}}{Q_{es} + Q_{ms}}$$

## Finding $Q_{ms}$ and $Q_{es}$

![[Pasted image 20231105222502.png]]

$Z_{max}$ = impedance at $F_s$
$Z_0 = \sqrt{R_e \times Z_{max}}$
find $F_1$ and $F_2$ in impedance curve ($F_1$ and $F_2$ have difference meaning from $F_3$)
$$Q_{ms} = \frac{F_s}{F_2 - F_1} \times \sqrt{\frac{Z_{max}}{R_e}}$$

```
 Qms = Fs/(F2 - F1)*sqrt(Zmax/Re)
```
$$Q_{es} = \frac{Q_{ms}}{\frac{Z_{max}}{R_e} - 1}$$
$$Q_{es} = \frac{F_s}{F_2 - F_1} \times \frac{\sqrt{Z_{max} \cdot R_e}}{Z_{max} - R_e}$$
```
Qes = Qms/(Zmax/Re - 1)
```

#### Relation with other variables

$$
Q_{es} = \frac{2\pi \cdot f_s \cdot M_{ms} \cdot R_e}{(Bl)^2} 
       = \frac{R_e}{(Bl)^2}\sqrt{\frac{M_{ms}}{C_{ms}}}
$$

$$
Q_{ms} = \frac{2\pi \cdot f_s \cdot M_{ms}}{R_{ms}} 
       = \frac{1}{R_{ms}}\sqrt{\frac{M_{ms}}{C_{ms}}}
$$


*ref.* [Measuring transducer Qms, Qes, Qts (wavecor.com)](http://www.wavecor.com/Measuring_driver_Q-values.pdf)

$C_{ms}$ - Compliance 
	Higher (loose suspension) -> yield a lower frequency
	Lower (stiffer suspension) -> yield a higher frequency



$R_e$ - DC resistance (normally 30% less than impedance)
Impedance, $Z$ - AC resistance


$Bl$ - Magnetic force factor / motor strength ($T \cdot Nm$)

$B \times l$. Which is (the flux density) x (the length of the voice coil)

Or, actually
$$
Bl = B \times l \sin{\theta}
$$
$$
\theta = 90 \degree,  \sin (90 \degree) = 1
$$
So,
$$
Bl = B \times l
$$

Relative to other parameters
$$
Qes = \frac{2\pi \cdot F_s \cdot Mms \cdot R_e}{Bl^2}
$$
$$
Bl = \sqrt{\frac{2\pi \cdot F_s \cdot Mms \cdot R_e}{Qes}}
$$
# Dimensions
## V

**Vas** - air volume equal equal to compliance of driver suspension (springiness of driver)
     = $C_{ms}$ describe in volume
 $$
 V_{as} = \rho \cdot c^2 \cdot S^2_d \cdot C_{ms}
 $$
**Vb** - Net enclosure internal volume


$Xmax$ - maximum distance that coin can travel without distortion
(they said that travel of 115% Xmax will not introduce audible distortion)

![[Xmax_1.png]]

![[Xmax_2.png]]

In 5-7" speaker $Xmax$ should be more than 3mm
In 8-12" speaker $Xmax$ should be more than 6mm

$Xmech$ - maximum distance a speaker can travel without damaging the driver

$> Xmax$  = Distortion
$> Xmech$ = Damage!!

Sd - effective area of the cone ($\pi r^2$)
more Sd = more bass
less Sd = more spread high frequency


Mmd = moving mass (mass of Coil + Cone + spider/2 + surround/2)
Mms = Mmd + mass of air in front of the cone

High Mmd -> Low $F_s$
Low Mmd -> High $F_s$

# SPL

[[Sound Power#SPL]]
## units 
- $dB\;@\;W/m$
- $dB\;@\;2.83V/m$

Difference driver Impedance will effect $dB\;@\;2.83V/m$ unit

$$
\begin{split}
	W &= V^2/Z \\
	  &= 2.83^2/8 \\
	  &= 8 / 8 \\
	  &= 1
\end{split}
$$
$$\begin{split}
dB\;@\;2.83V/m\;@\;8\ohm &= \pm 0\;dB\;@\;W/m \\
dB\;@\;2.83V/m\;@\;6\ohm &= -1.3\;dB\;@\;W/m \\
dB\;@\;2.83V/m\;@\;4\ohm &= -3\;dB\;@\;W/m \\
dB\;@\;2.83V/m\;@\;2\ohm &= -6\;dB\;@\;W/m \\
\end{split}
$$
twice the power give +3 dB
half the power give -3 dB
one tenth the power give -10 dB

$$\Delta dB =10 \log(\frac{P_1}{P_2})$$

### Ex
$$
\begin{array}{rcl}
 1\;W &\Rightarrow &90\;dB \\
 2\;W &\Rightarrow &93\;dB \\
 4\;W &\Rightarrow &96\;dB \\
 8\;W &\Rightarrow &99\;dB \\
 10\;W &\Rightarrow &100\;dB \\
 16\;W &\Rightarrow &102\;dB
\end{array}
$$

## Max SPL
$$Max\;SPL = Efficiency\;@\;W/m + 10 \times \log(Max Power)$$
## Perceived loudness
- 3 dB difference is difficult to hear
- 10 dB considered to be twice as loud

# $\eta\;(n_0)$ Efficiency

1 Watt of acoustic power = 112 dB SPL 1W/1m

$$SPL = 112 + 10 \log{\eta}$$
$$\eta = 10^{\frac{SPL - 112}{10}}$$
   
|**Efficiency**|**Percent**|**Sensitivity**|
|---|---|---|
|0.2|20 %|105 dB|
|0.1|10 %|102 dB|
|0.05|5 %|99 dB|
|0.02|2 %|95 dB|
|0.01|1 %|92 dB|
|0.005|0.5 %|89 dB|
|0.002|0.2 %|85 dB|
|0.001|0.1 %|82 dB|

## $\eta$ relation to other parameters

$$
\eta = (\frac{\rho \cdot B^2 \cdot l^2 \cdot S^2_d}{2\pi c \cdot M^2_{ms} R_e}) \times 100 \%
$$
$$
\eta=(\frac{4\pi^2 \cdot f^3_s V_{as}}{c^3 \cdot Q_{es}}) \times 100\%
$$

** $\rho/2\pi = 5.365×10^{−4} \;m^2·s/kg$ 
** $4\pi^2 / c^3 = 9.523×10^−7\;s^3/m^3$
** @ 25 °C and 50% humidity


*ref.* [Efficiency and sensitivity conversion - sengpielaudio Sengpiel Berlin](http://www.sengpielaudio.com/calculator-efficiency.htm)

## Hofmann's Iron Law

$$\eta = k \cdot V_b \cdot f_3^3$$


