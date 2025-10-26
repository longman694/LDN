Short answer: treat the driver as a baffled piston and convert its maximum displacement into a maximum volume-velocity; use the monopole far-field formula to turn that into RMS sound pressure, then convert to dB. Below are the exact formulas, a quick example, and the usual caveats.

# Formula (on-axis, far field, 1 m reference)

Let
- $S_d$ = piston area (m²)
- $⁡X_{\max}$ = one-sided peak excursion (m)
- $f$ = frequency (Hz), $\omega = 2\pi f\;(rad/s)$
- $r$ = distance (m) (use $r=1$ m for the usual 1 m SPL reference)
- $\rho_0$ = air density ≈ 1.21 kg/m³
- $p_{ref}=20\times 10^{-6} Pa$ (SPL at 0 dB)

Volume-velocity (RMS) for a sinusoid:

$$
Q_{\text{rms}} = S_d \cdot \frac{\omega X_{\max}}{\sqrt{2}}
$$

Far-field RMS pressure (monopole approximation for a small baffled piston):

$$p_{\text{rms}} = \frac{\rho_0\,\omega\,Q_{\text{rms}}}{4\pi r} = \frac{\rho_0\,S_d\,\omega^2\,X_{\max}}{4\pi r\sqrt{2}}$$

Maximum SPL limited by excursion (RMS → dB):

$$
\mathrm{SPL}_{\text{excursion}}(f) = 20\log_{10}\!\left(\frac{p_{\text{rms}}}{p_{ref}}\right) =20\log_{10}\!\left(\frac{\rho_0 S_d \,\omega^2 X_{\max}}{4\pi r\sqrt{2}\,p_{ref}}\right)
= 20 log_{10}(\frac{\rho_0 \pi S_d f^2 X_{\max}}{r\sqrt{2}\,p_{ref}})
= 20 log_{10} (134397.208879 \cdot S_d f^2 X_{max})
$$

If you want peak dB (not RMS) add +3 dB to the RMS value.

# Inverse - what Xmax you need for a target SPL at frequency f

Solve for $X_{\max}$:

$$
X_{\max} = \frac{4\pi r\sqrt{2}\,p_{ref}}{\rho_0 S_d \,\omega^2}\times 10^{\mathrm{SPL}/20}
$$

# Quick numeric example

Take $S_d=0.03\ \mathrm{m}^2$ (≈ 8″ driver), $X_{\max}=6\ \mathrm{mm}=0.006\ \mathrm{m}$, $f=50\ \mathrm{Hz}$, $r=1\ \mathrm{m}$:  
Using the formulas above gives $p_{\text{rms}}\approx 1.21\ \mathrm{Pa}$ and  
$\mathrm{SPL}\approx 95.6\ \mathrm{dB}$ (RMS, 1 m). Peak SPL ≈ 98.6 dB.

# Important caveats (don’t ignore these)

- This is a _theoretical_ excursion limit only. It ignores electrical power limits, thermal power handling, voice-coil nonlinearity, suspension nonlinearity, and driver resonance behavior. In practice you’ll hit other limits earlier.
    
- The mono far-field/piston approximation is valid when the driver behaves like a piston (low frequency compared to breakup, and the driver is mounted on a large baffle or in an enclosure). At higher frequencies directivity and piston breakup change the result.
    
- Room/woofer placement, enclosure type (sealed, ported), and acoustic loading change the SPL for a given displacement; a ported box can give much higher SPL near tuning frequency for the same cone excursion.
    
- The formula assumes on-axis and free-field; off-axis or room reflections change measured SPL.
    
- Use RMS SPL for comparisons to standards; humans perceive peak bursts differently.
