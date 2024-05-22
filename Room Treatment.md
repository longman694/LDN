First thing first, overly room treatment is bad.
Your brain want to hear some reflection.
(Think of first generation noise canceling headphone)

You don't want to live in an [anechoic chamber](https://en.wikipedia.org/wiki/Anechoic_chamber)

15 - 20% Absorption surface (absolute not more than 20%)
- Distributed evenly
- Lower reflected energy

15 - 20% Diffusion surface
- Interleaved with absorption
- 2D in front of room, 3D in back -> make room feel bigger
- Improves spaciousness

Include ceiling
- vertical reflection narrow the sound

Base absorption
- Bass reflection reduce dynamics

### 5 ms delay law

The brain will treat the same sound delayed by 5ms as a reflection and cut it off from your perception.



# Absorber
- Need thickness, the thinker it is the lower frequency it can absorb
	- $\frac{434\;m/s}{1000\;Hz} = 43.4\;cm$ ; 1000 Hz need 2.5 cm <- bad
	- $\frac{434\;m/s}{500\;Hz} = 86.8\;cm$ ; 500 Hz need 5 cm <- best compromise
	- $\frac{434\;m/s}{250\;Hz} = 173.6\;cm$; 250 Hz need 10 cm <- best absorption
- For thick absorber, make its surface curve it will look less ugly
- Lift the absorber away from the wall will increase absorption, like 5 - 10 cm
	- ex. use 5 cm absorb and lift it 5 cm from the wall
- Asymmetrical layout is better
- don't "over absorb"
	- Target reflection decay time: less than -60 dB with in 0.3 sec (roughly 0.2 - 0.4 sec)

# Placement
Target decay time of the room 
$$T_m=0.3\times(\frac{V}{100})^\frac{1}{3}\pm15\%$$
V = room volume in $m^3$

At lower frequency, Upper bound 
63 $Hz$ - $T_m$ can be 100% longer, linearly scale to 15% at 200 $Hz$

At higher frequency, lower bound
4 - 8 $kHz$ - $T_m$ can be 50% shorter

The Eyring equation

$$RT60 = \frac{0.161V}{-S\ln{(1-\alpha)}}$$
$RT60$ is the decay time of 60 $Hz$
$V$ is volume $(m^3)$
$S$ is total room surface area $(m^2)$
$\alpha$ is area-weighted averaged absorption coefficient


# Cloth - Acoustic Transparent Fabric
- fabric that allow air to pass easily
- JUST BLOW IT!!
- More accurate method -> play pink noise the put fabric between you and speaker
- transparent up to 6 kHz for treatment
- transparent up to 16 kHz for speaker front



# Diffuser

- target frequency 500 - 3000 Hz 

- wave length $\gg$ object width  -> pierce through
- wave length $\approx$ object width -> scatter
- wave length $\ll$ object width -> reflect

[Calculator with given Column width & max. Column length (mh-audio.nl)](http://www.mh-audio.nl/Acoustics/DiffusorCalculator3.asp?km=3&kl=10&calc=Calculate+Diffuser#result)

![[Pasted image 20231029031232.png]]


![[Pasted image 20231029031109.png]]