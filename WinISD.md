#WinISD 

# Introduction to equivalent circuits

These are the models which WinISD graph calculations are based on. Models are documented here for reference. Most box-program authors are not documenting publicly these things. They are also useful, if someone wishes to evaluate validity of used models. Most people don't need these.

Circuits are reduced to acoustical side. Models for currently supported enclosure types are:

- Closed box
- Vented box
- Passive radiator
- 4th order bandpass
- 6th order bandpass type A

Voltage source, Uad, is so called "constant pressure generator". Resistance models acoustic resistance, capacitor models compliance (volumes) and inductor models mass. There are several ways to determine component values. One, which is used in WinISD pro, is where we start on driver Vas to determine Ccas:  
  
Ccas = Vas/(roo·c²)  
  
Then, we'll use fs to determine Lmas:  
  
Lmas = 1/((2·pi·fs)²·Ccas)  
  
Then, Qes and Qms is used to determine Rae and Ram:  
  
Rae = 1/(2·pi·fs·Qes·Ccas)  
Ram = 1/(2·pi·fs·Qms·Ccas)  
  
Now, we'll calculate box volume modelling capacitor Ccab just like Ccas. If we have closed box, we'll have only determine the leak and absorption modelling resistors. These are determined by so called Q-factors. For lack of better models, these are determined at resonance frequency of boxed driver.

### Determining frequency response

When all component values are in place, then we'll just simulate completed circuit, using any circuit simulation program, e.g. SPICE (**S**imulation **P**rogram with **I**ntegrated **C**ircuit **E**mphasis). Frequency response is calculatable from determining the volume velocity through Ccab. Using one well-known relation, we can get to far-field pressure value from volume velocity:  
  
p(r) = roo·s·U0(w)/(2·pi·r)·exp(-j·k·r)  
  
where k is so called wave number (k=w/c), and r is distance from diaphraghm. U0 is total volume velocity produced by box. If there is only one chamber, then U0 is current through Ccab. If there are several chambers, like in bandpass enclosures, then total volume velocity is **vector** sum of all volume velocities of chambers. Latter exp()..-part is the phase factor (which has always gain of unity), which is neglected in WinISD, in order to show more clear graph. Pressure is therefore complex valued. Now, when we have obtained absolute pressure level, we may use reference pressure of 20 μPa, the 0 dB reference.

### Group delay

Group delay can be extracted from frequency response data by numerically derivating the phase by mathematical definition: gd(w)=-d(arg(H(f)))/dw, where arg(H(f)) is phase part of transfer function. In practice, it is done by just calculating two phase values on very small interval, and then just approximating above differential by (arg(H(f+d))-arg(H(f-d)))/(2·d).

### Cone excursion

Cone excursion is calculated by first determining volume velocity through driver. Then, volume velocity is integrated, and the result is then divided by Sd to get cone excursion. Still, we need to scale result by sqrt(2) if we want to get peak value and 2·sqrt(2) if we want peak-to-peak value.

### Port velocity

Port velocity is like cone excursion. Again, volume velocity through port is determined. Since we need port velocity, then, we just divide volume velocity by port area. This gives us RMS port velocity, which is optionally scaled, like cone excursion.

### Impedance

Impedance is calculated by first calculating acoustical impedance seen by Uad and Rae is subtracted. By using conversion formula, Zem = Bl²/(Sd²·Za), where Za is aforementioned acoustical impedance and Zem is additional motional impedance reflected from mechanical circuit. Then final electrical impedance Ze is calculated by Ze = Re + jw·Le + Zem. All impedances are complex.


## Closed box

![[Pasted image 20231126113230.png]]

## Vented box

![[Pasted image 20231126113338.png]]

## Passive radiator

![[Pasted image 20231126113413.png]]

## 4th order bandpass

![[Pasted image 20231126113345.png]]

## 6th order bandpass type A

![[Pasted image 20231126113403.png]]

