- also called bass reflex
# Pros
- boost specific frequency below **Fs**
- Reduced distortion
- Higher power
# Cons
- Steep dropout (-24dB/Octave)
- Need to be calculated precisely
- Larger than sealed
- port can be noisy

## Parameters

### 1. Speaker Fs and other T/S parameters

- This is for simulate characteristic of the speaker.
- Adding vent will boost the frequency slightly below Fs.

### 2. Size of Enclosure ($V_b$)
- the bigger the lower frequency boost
- don't forget to calculate volume of the speaker
	- add volume of a hole
	- subtract rigid part of the speaker

### 4. Boost frequency
- Use WinISD to help
- Use [Online Tone Generator](https://onlinetonegenerator.com/) for help
	- Low bass (<40 Hz) is only good for movies
	- Mid bass (40-60 Hz) is not matter much in music
	- Upper bass (60-120 Hz)
	- Kick drum is around 40-100 Hz
- 2 Strategies
	- As flat as possible
	- Boost for compensate [[Loudness]] 

### 3. Vent Size
- Need to be simulated
- Good starting point of vent area is around 3.6 cm^2/l 
- In WinISD, set signal source input power and then change graph to air velocity
	- Good air speed should below 5% of speed of sound in the air (343 m/s)
	- < 17 m/s (< 20 m/s should also be fine)
	- If you use flare port (filleted port) you may use 10% of speed of sound
	- < 30 m/s and don't forget to cut port length by esposimate 
	- more air velocity = higher turbulence = higher distortion 
- Bigger vent area = lower air velocity = longer vent
- smaller vent area = higher air velocity = shorter vent


### 4. Q Leakage

This slightly effect the final wave.

$Qlt$ or $Qb$- Q leakage total is depended on 3 values

$Ql$ is the Q-value due to unwanted enclosure and woofer leakage losses  
${Qa}$ is the Q-value due to enclosure damping material (or absorption losses)  
${Qp}$ is the Q-value due to port losses  

Which
$$ \dfrac{1}{Qlt} = \dfrac{1}{Qa} + \dfrac{1}{Ql} + \dfrac{1}{Qp} $$

In normal cases Ql is in the range 5-20. Ql is 7 in most cases, but 15 to 30 if the enclosure has very little leakage. Ql may be 7 even with an enclosure with no leakage because the driver unit itself may have leakages.  
  
A box with moderate lining has a Qa of about 30. A heavily stuffed box can have a Qa of 3. Qa is 7 for about a half-filled enclosure.  
  
A perfect port will have absolutely no losses in which case Qp is very large. A good port, one which does not significantly restrict air flow, has about 100 of Q-value.


Measurements of Ql, Qa and Qp are difficult unless you can assume that all the others are negligible when measuring one of them - which is not realistic in most cases.  
  
The values Bullock uses as default:  
Ql=14  
Qa=28  
Qp=28  

Bullock's values give you a Qlt of 7  

When running sims, I use:  
For vented boxes  
Ql=15  
Qa=30  
Qp=30  

Sometime Ql can be selected by enclosure size

|  Ql    |  Size (l)  |
| ------- | ---------- |
| 3 - 5   | > 70       |
| 7       | 35 - 70    |
| 10 - 15 | < 35       |

## 5. Alignment

### Flat
1. **SBB4 or Super Forth-Order Boom Box** – is characterized by a large box, low tuning frequency (longer vent) and good transient response (which puts the term boom-box out of place).
2. **SC4 or Forth-Order Sub-Chebyshev** – about the same enclosure size and f3 as the SBB4, but with different tuning frequency. Somewhat degraded transients compared to SBB4.
3. **QB3 or Third-Order Quasi-Butterworth** – is the most popular vented alignment, because it yields a smaller box and a lower f3. However, the transient response is not as good as SBB4 or SC4.
4. B4 Forth-Order Butterworth
5. BE4 Forth-Order Bessel
6. IB4 Butterworth Inter-Order

### None-flat
1. **C4 or Forth-Order Chebyshev** – can be useful for low values of ripple (less than 1 db).
2. **BB4 or Forth-Order Boom Box** – has a peak in response close to roll-off, similar to high Qtc sealed boxes (1.2 or higher).
3. **SQB3 or Super Third-Order Quasi-Butterworth** – is a high value Qts extension of the QB3 alignment.

## 6. Measurement
when measurement speaker and port
you need to adjust port SPL using this formula

$As$ = Area of speaker same as $Sd$ from [[Thiele-Small Parameters|T/S parameters]]
$Ap$ = Area of port

$$Adjust = 20\times\log(\sqrt\frac{Ap}{As})$$

# Port in-depth

$D_v$ - diameter of circular port in cm
$N_p$ - Number of ports
$k$ - correction
$V_b$ - Box Volume in litters
$L_v$ - port length in cm

$$f_b = \frac{c}{2\pi}\sqrt{\frac{\pi\cdot (\frac{D_v}{2})^2 N_p}{V_b(L_v + kD_v)}}$$

$$f_b = \sqrt{\frac{2.35625\times10^4 \cdot D_v^2 N_p}{V_b(L_v + kD_v)}}$$

$$L_v = \frac{10c^2}{16\pi} \cdot \frac{D_v^2N_p}{V_bf_b^2} - kD_v$$

$$L_v = \frac{2.35625 \times 10^4 \cdot D_v^2 N_p}{V_bf_b^2} - kD_v$$

## $D_v$ of other shape with Hydraulic Diameter

### Square duct

a = Width of the duct
b = Height of the duct

Without hydraulic effect

$$D=2\sqrt{\frac{ab}{\pi}}$$

Normal
$$D = \frac{2ab}{a+b}$$
ASHRAE's
$$D = 1.3 \cdot \frac{(a \cdot b)^{0.625}}{(a+b)^{0.25}}$$
### Oblong ducts

![[Pasted image 20231025135504.png]]
$$D=1.55 \cdot \frac{(\pi\frac{b^2}{4}+ab+b^2)^{0.625}}{(\pi b + 2a - 2b)^{0.25}}$$
<code>(1.55*(pi*b*b/4+a*b+b*b)**0.625/(pi*b+2*a-2*b)**0.25)</code>

https://www.thermexcel.com/english/ressourc/no_circul.htm
## $k$

![[Pasted image 20231025123608.png]]
free = 0.307
flanged = 0.425

**Both ends flanged: k = 0.425 + 0.425 = 0.850  
One end flanged, one end free: k = 0.425 + 0.307 = 0.732  
Both ends free: k = 0.307 + 0.307 = 0.614**


![[Pasted image 20231025125245.png]]

# Port Flare

Since the air in the port needs to meet the flat front baffle I imagine that as x -> 0, r -> infinity. This boundary condition is met by any radius chamfer.  
  
If port compression is caused by turbulence then we want laminar flow. From the Wikipedia [article](https://en.wikipedia.org/wiki/Laminar_flow) that suggests we want the Reynolds number of the fluid to stay below 1800.  
  
Assume the narrowest part of the port occurs at $x=m$ and that $R_e = 1800$ at that point. How should the port's radius change to not increase Re while growing at the fastest rate possible?  

$$
R_e = \frac{QD}{\nu A}
$$

$D$ is the hydraulic diameter of the pipe ($m$) (which for round completely full pipes is $2\times$ the radius)  
$Q$ is the volumetric flow rate ($m^3/s$)  
$A$ is the pipe's cross-sectional area ($m^2$)  
$u$ is the mean speed of the fluid (SI units: $m/s$);  
$ν$ is the kinematic viscosity of the fluid  

$$
R_e = \frac{2Qr}{\nu \pi r^2}
$$
  
Group all the constant terms into a coefficient K  

$$
R_e = \frac{Kr}{r^2} = \frac{K}{r}
$$
  
So any increase in r will reduce Re. This implies any increasing are would meet the criteria. But clearly, in real life, it helps to have a more gradually expanding port. I tried to come up with an equation that considers both the axial and radial velocity of air particles, but no luck yet.  

Regarding the use of a 3D printer and more complicated geometries, it is not necessary for sure. I find this to be part of the fun.

*ref.* https://www.diyaudio.com/community/threads/optimal-port-flare-geometry.377259/

# Reference

- [Bass reflex alignments explained - Step by step - Audio Judgement](https://audiojudgement.com/bass-reflex-alignments-explained/)
- http://www.mh-audio.nl/Calculators/WVC.html#volume
- http://www.troelsgravesen.dk/vent_tuning.htm
