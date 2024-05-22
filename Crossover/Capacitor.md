
## Dissipation factor

<img style="background: white;" src="https://upload.wikimedia.org/wikipedia/commons/6/61/Loss_tangent_phasors_1.svg">

## ESR

**Why is ESR important?**

Electrolytic capacitors are used as input buffers to supply energy when the mains input voltage is too low, store energy while an AC/DC converter adapts to a new power level, and prevent switching noise from the converter reaching the power source. On the output of a converter, they act as a filter and current sink for inductive elements, and, in DC/DC conversion, function as an energy buffer when the power output demand changes.

In both cases, losses due to ESR will inhibit a capacitor’s ability to quickly source or sink charge. At the input, increasing ESR increases high frequency noise across the capacitor, decreasing filtering effectiveness. At the output, higher ESR causes more ripple, influencing stability of the control loop.

ESR is particularly important in applications with low duty-cycle, high-frequency current pulses. Here, the ripple voltage due to the ESR will be greater than expected based on capacitance alone, although the negative correlation of ESR with temperature means that ripple decreases as the assembly warms up.

Also, the introduction of a resistive element into what designers may assume is a purely reactive circuit can lead to unexpected shifts in phase response, again affecting stability.

ref. https://www.avnet.com/wps/portal/abacus/resources/article/understanding-esr-in-electrolytic-capacitors/

# Clarity Cap
Super hi-end
http://www.claritycap.co.uk/products/pur.php

# Dayton
https://www.samdee-audio.com/category/60/capacitor-for-crossover-network/dayton-audio-capacitor
# Solen
https://www.samdee-audio.com/category/59/capacitor-for-crossover-network/solen-capacitor

# Solen (counterfeit)
https://shopee.co.th/เน็ตเวิร์ค-คาปาซิเตอร์เกรดออดิโอ-สีดำ-400V-i.44695276.5819055380

# MDL 
https://www.samdee-audio.com/category/92/capacitor-for-crossover-network/m-d-l-capacitor


# Spec 



$$X_c = \frac{1}{2\pi fC}$$
DF - Dissipation Factor

$$DF = tan(\delta) = \frac{ESR}{X_c}$$

ESR - Equivalence Serial Resistance
$$ESR = tan(\delta) \cdot \frac{1}{2\pi fC}$$



# Capacitors Measurement


| Name           | C ($\micro F$) | F (Hz) | ESR ($\ohm$) | DF (%)   | Q      | $\delta$ ($\deg$) |
| -------------- | -------------- | ------ | ------------ | -------- | ------ | ----------------- |
| Nichi P 22     | 20.99          | 120    | 1.938        | 3.071    | 32.57  | 1.759             |
|                |                | 1k     | 1.06         | 1.06     | 13.57  | 7.369             |
|                |                | 10k    | 0.6702       | 106.4    | 0.9403 | 46.76             |
| Nichi BP 47    | 45.51          | 120    | 1.373        | 4.657    | 21.47  | 2.666             |
|                |                | 1k     | 0.7096       | 19.64    | 5.091  | 11.11             |
|                |                | 10k    | 0.3606       | 162.5    | 0.6153 | 58.4              |
| Solen 2.2      | 2.18           | 120    | 33.26        | 5.457    | 18.33  | 3.124             |
|                |                | 1k     | 0.007102     | 0.009733 | 10280  | 0.005576          |
|                |                | 10k    | 0.4926       | 6.754    | 14.81  | 3.864             |
| Solen 47       | 47.04          | 120    | 0.4276       | 1.517    | 65.93  | 0.869             |
|                |                | 1k     | 0.5066       | 15.09    | 6.625  | 8.583             |
|                |                | 10k    | 0.2994       | 140.9    | 0.7095 | 54.64             |
| OHVL white 2.2 | 2.195          | 120    | 31.49        | 5.22     | 19.16  | 2.988             |
|                |                | 1k     | 0.3108       | 0.4289   | 233.2  | 0.2457            |
|                |                | 10k    | 0.561        | 7.686    | 13.01  | 4.395             |
| OHVL blue 2.2  | 2.185          | 120    | 33.31        | 5.476    | 18.26  | 3.135             |
|                |                | 1k     | 0.007061     | 0.009681 | 10330  | 0.005547          |
|                |                | 10k    | 0.4912       | 6.753    | 14.81  | 3.863             |
| Nichi + OHVL   | 47.78          | 120    | 1.298        | 4.621    | 21.64  | 2.646             |
|                |                | 1k     | 0.6879       | 20.05    | 4.988  | 11.34             |
|                |                | 10k    | 0.3436       | 165.6    | 0.6039 | 58.87             |
