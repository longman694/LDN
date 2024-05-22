# Sound Power $(P)$

$$P = \frac{Ap^2}{\rho c} \cdot cos\theta$$
- $A$ is the area of the surface;
- $\rho$ is the [mass density](https://en.wikipedia.org/wiki/Mass_density "Mass density");
- $c$ is the [sound velocity](https://en.wikipedia.org/wiki/Sound_velocity "Sound velocity");
- $\theta$ is the angle between the direction of propagation of the sound and the normal to the surface.
- $p$ is the [sound pressure](https://en.wikipedia.org/wiki/Sound_pressure "Sound pressure").

In air, $\rho = 1.2 \;kg/m^{3}$ and $c = 343 \;m/s$

Sound Pressure Level SPL $L_p$ - $(dB)$

Sound pressure $p$ $(N/m^2)$ or $(Pa)$

$$L_p = 20 \log \frac{p}{p_0}$$
where $p$ is sound pressure in pascals $(Pa)$
and $p_0 = 20\; \micro Pa$ accordance with ISO 1683.
$p_0$ comes from lowest sound pressure that human can hear at $3,000-4,000 \;Hz$

# Sound Level $(L)$  vs  Distance $(r)$
$$L_1 - L_2 = |20 \cdot \log\frac{r1}{r2}|$$
Sound level drop by 6 dB per double the distance.


# Sound intensity $(I)$
$$P = AI$$
where
- _A_ stands for the area;
- _I_ stands for the sound intensity.

# Sound energy density $(\omega)$
$$P=Ac\omega$$
where
- _c_ stands for the [speed of sound](https://en.wikipedia.org/wiki/Speed_of_sound "Speed of sound");
- _w_ stands for the sound energy density.

## Calculator
https://mehlau.net/audio/spl/

```js
function doCalc() {
	var efficiency = eval(formSPL.efficiency.value * 1)  // SPL (1W/1m)
	var dBPower = eval(10 * (Math.log(formSPL.power.value) / Math.log(10)));  // Amp Power Watt
	var dBDistance = eval(-20 * ((Math.log(formSPL.distance.value) / Math.log(10)))); // m
	var dBPlacement = eval(formSPL.placement.value);
	var dBResult = eval(efficiency + dBPower + dBDistance + dBPlacement * 1);  // dB
	dBResult = round(dBResult, 1);
	formSPL.result.value = dBResult;
}

<option value="0">Away from walls</option>
<option selected value="3">Close to wall (60-120cm)</option>
<option value="6">In corner (45-60cm)</option>
```
# SPL 
[[Thiele-Small Parameters#SPL]]

SPL @ 1W/1m

**How many decibels (dB) are doubling a sound**

 $\times 2$ the sound intensity is **+3 dB.**  
 $\times 2$  the sound pressure is **+6 dB.**  
 $\times 2$  the loudness feeling is about **+10 dB.**

 $\times 2$ the power (Watt) is **+3 dB.** 10 dB = 10-fold
 $\times 2$ the Voltage $(V)$ or Current $(I)$ is **+6 dB.** 20 dB = 10-fold

ref. [Damping of sound level](http://www.sengpielaudio.com/calculator-distance.htm)

[**The human perception of loudness**](http://www.sengpielaudio.com/calculator-loudness.htm)


|**Pressure Level Change**|**Volume Loudness**|**Voltage / Sound pressure** | **Acoustic Power / Sound Intensity**|
|---|---:|---:|---:|
|+40 dB|16|100|10000|
|+30 dB|8|31.6|1000|
|+20 dB|4|10|100|
|**+10 dB**|**2 double**|3.16 = $\sqrt{10}$|**10**|
|+6 dB|1.52 times|**2 double**|4|
|+3 dB|1.23 times|1.414 times = √2|**2 double**|
|±0 dB|**- - - 1.0 - - - **|**- - - 1.0 - - -**|**- - - 1.0 - - -**|
|−3 dB|0.816 times|0.707 times|**0.5 half**|
|−6 dB|0.660 times|**0.5 half**|0.25|
|**−10 dB**|**0.5 half**|0.316|0.1|
|−20 dB|0.25|0.1|0.01|
|−30 dB|0.125|0.0316|0.001|
|−40 dB|0.0625|0.01|0.0001|
|**Log. size**|**Psycho size**|**Field size**|**Energy size**|
|**dB change**|**Loudness multiplier**|**Amplitude multiplier**|**Power multiplier**|




# From Genelec
https://www.genelec.com/correct-monitors

## Sound Basics

Sound is ultimately pressure which exists in a sequence of waves which propagates through compressible media such as air or water. Sound travels approximately 344 m/s (1130 ft/s). It takes 3 ms for sound to travel 1 metre (3,3 ft).

In free-field conditions (no walls, floor, or ceiling) the sound volume drops 6 dB when the distance doubles.

|Distance|Sound Level|Volume Drop|
|---|---|---|
|1 m|100 dB|0 dB|
|2 m|94 dB|-6 dB|
|4 m|88 dB|-12 dB|

Sound level increases by 3 dB when the amplifier power doubles.

|Amp Power|Sound Level|Volume Increase|
|---|---|---|
|100 W|85 dB|0 dB|
|200 W|88 dB|+3 dB|
|400 W|91 dB|+6 dB|

The industry standard reference sound pressure level (SPL) for cinema and TV sound production work is between 82 and 85 dB at the listening position.

### Frequency Spectrum

The frequency spectrum of an electrical signal is, by definition of Collins online dictionary, "the distribution of the amplitudes and phases of each frequency component against frequency". The audible frequency spectrum covers 10 octaves (up to 40 Hz, 80, 160, 320, 640, 1’280, 2’560, 5’120, 10’240, 20’480 Hz) which can conveniently divide the spectrum as follows.

|Subsonic bass frequencies|below 16 Hz|Not audible for humans.|
|---|---|---|
|Very low frequencies|16 – 40 Hz  <br>40 – 80 Hz|Lowest audible octave for humans.  <br>Music low frequencies, kick drums, bass instruments|
|Low frequencies|80 – 160 Hz  <br>160 – 320 Hz|Low register of a grand piano.  <br>Middle C of a piano.|
|Midrange frequencies|320 – 1,280 Hz|Music midrange frequencies|
|Upper midrange frequencies|1,280 – 2,560 Hz  <br>2,560 – 5,120 Hz|Low-order harmonics of most instruments.  <br>The ear is the most sensitive in this range.|
|High frequencies|5,120 – 10,240 Hz|Brightness and harmonics|
|Extremely high frequencies|10,240 – 20,480 Hz|Highest harmonics. Inaudible to humans above 20 kHz|


![[Pasted image 20231126013245.png]]