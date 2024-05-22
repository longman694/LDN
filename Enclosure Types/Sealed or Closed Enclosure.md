- $V_b < Vas$
# Pros
- Efficient
- Low distortion
- Easier to build
- Smooth base dropout
- Some varies of box volume is not effect much
# Cons
- Low Efficiency

## Qtc

Qtc = Total Q (speaker + box)
Qts = Qms and Qes
Qtc = Qbox and Qts

|Qtc|Response Peak|Character|
|---|---|---|
|0.500 (Linkwitz-Riley)|0|Critically damped, lowered SPL, huge enclosure|
|0.577|0|Optimal driver damping, lowered SPL, best transient response, huge enclosure|
|0.707 (Butterworth)|0|Usually considered the "optimum" alignment by most designers, gives excellent transient response, low bass performance and power handling, and flattest response curve before F3. Enclosure may be fairly large.|
|0.850|+0.69 dB|Good alignment if optimum is to large an enclosure, generally very good performance with only slightly accentuated (non-flat) bass, good low bass response. Medium sized enclosure.|
|1.000|+1.25 dB|Best compromise enclosure. Much smaller box than optimum, fair transient response and low bass performance, more noticeable midbass peak. Medium-smaller sized enclosure.|
|1.100|+1.83 dB|Maximum power handling and efficiency, smaller sized enclosure, more pronounced midbass peak. Smaller enclosure.|
|1.300|+3 dB|Driver may sound noticeably boomy, especially smaller drivers with higher Fs and Qts. Fair (or worse) transient response and compromised low bass response. Pronounced mid-bass peak makes the enclosure louder but less accurate. Small enclosure.|
|2.000|+6 dB|Very boomy and muddy, poor transient response and low bass performance. Very small enclosure.|

\> 0.7 call Chebyshev
## Q Value

Ql loss of the box
Qa loss of the absorb material 

For sealed boxes (lined):  
Ql=15  
Qa=20  
  
or some other combo to get Qlt=~10  
  
For sealed boxes (stuffed):  
Ql=15  
Qa=8  
  
or some other combo to get Qlt =~5

### Stuffing
Isothermal propagation??
Stuffing dumping material in the box can increase box size


# Box Volume ($V_b$) Calculation
$$V_b = \frac{V_{as}}{(\frac{Qtc}{Qts})^2 - 1}$$
$$\frac{V_{as}}{V_b} = (\frac{Qtc}{Qts})^2 - 1$$

```python
Vb = Vas / ((Qtc/Qts)**2 - 1)

Vas = Vb * (Qtc/Qts)**2 - Vb
```

$$f_b=f_s\cdot \sqrt{\frac{V_{as}}{V_b+1}}$$
```python
fb = fs * (Vas/(Vb+1))**0.5

fb = fs * (Vas/(Vas / ((Qtc/Qts)**2 - 1)+1))**0.5

fb = fs * ( Vb * ((Qtc/Qts)**2 - 1) /(Vb+1))**0.5

```
$$f_3 = \frac{f_b}{\sqrt{2}} \cdot \sqrt{ (\frac{1}{Q_{tc}^2}-2) + \sqrt{(\frac{1}{Q_{tc}^2} - 2)^2 + 4}}$$
```python
f3 = fb / 2**0.5 * ((1/Qtc**2 - 2) + ((1/Qtc**2-2)**2 + 4)**0.5)**0.5
```
