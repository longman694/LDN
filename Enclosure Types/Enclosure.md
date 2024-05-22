
# Calculate Enclosure Size

Look at [[Enclosure Dimension Ratio|golden ratio of enclosure]]

---

# Types

- [[Infinite Baffle]]
- [[Sealed or Closed Enclosure]]
- [[Vented or Ported Enclosure]]
- [[Passive Radiator Enclosure]]
- [[Bandpass Enclosure#4th order enclosure|4th order enclosure]]
- [[Bandpass Enclosure#6th order enclosure|6th order enclosure]]
- [[Transmission Line]]
- [[Horn Loudspeaker]]
- [[ABC]]

## How to select enclosure type

First, you need to get [[Thiele-Small Parameters]] from speaker datasheet or measure by yourself.

**Generally**
- Bass reflex is +3dB louder than sealed.
- Bandpass has a narrower frequency response bandwidth, compared to bass reflex.

### Hoffman's Iron Law
Choose 2 of
- Enclosure size
- Efficiency
- Low-end extension (deep bass)

### 1. EBP (Efficiency Bandwidth Product)

$$EBP = \dfrac{Fs}{Qes}$$

| EBP      | Recommended |
| -------- | ----------------- |
| < 50     | [[Sealed or Closed Enclosure\|Sealed]] or [[Bandpass Enclosure#4th order enclosure\|4th order]] |
| 50 - 100 | Either |
| 100 - 130| [[Vented or Ported Enclosure\|Vented]] or [[Bandpass Enclosure#6th order enclosure\|6th order]] |
| > 130    | [[Horn Londspeaker]]|


### 2. Qts

|   Qts   | Recommended |
| ------- | ----------- |
|< 0.4    | [[Vented or Ported Enclosure \|Vented]]      |
|0.4 – 0.7| [[Sealed or Closed Enclosure\|Sealed]]      |
|> 0.7    | free-air or infinite baffle application|
|~ 0.7    | Most compatible with [[Transmission Line]]|


## 3. Isobaric drivers
[[Isobaric loading]]
- Put 2 speakers series to each other (magnet to cone) or facing each other (cone to cone)
- same $Fs$, same $Qts$
- but **cut $Vas$ in half**
- so smaller enclosure can be build
