big speakers tense to beam the sound

Main idea using [Huygens principle](https://en.wikipedia.org/wiki/Huygens%E2%80%93Fresnel_principle) to describe the angle


<img src="sound through slit.png" style="background-color:white">

## Intensity equation

$$
I(\theta) = I_0\ sinc^2(\frac{d\pi}{\lambda}\sin\theta)
$$
where 
$d$ is the slit width
$\lambda$ is a wave length
$\theta$ is a angle
$$
sinc(x\pi) = \frac{\sin (x\pi)}{x\pi}
$$
values of $sinc(x\pi)$

|           x           | $sinc(x\pi)$ | $sinc^2(x\pi)$ |
| :-------------------: | :----------: | :------------: |
|           1           |      0       |       0        |
|         0.99          |     0.01     |     0.0001     |
|         0.603         |     0.5      |      0.25      |
|         0.443         |    0.707     |      0.5       |
|         0.25          |     0.90     |      0.81      |
|          0.1          |    0.984     |     0.967      |
|         0.075         |     0.99     |      0.98      |
| $\lim(x\rightarrow0)$ |      1       |       1        |

let say, we're only interested in 90° from slit, so $\sin\theta=1$

If we want to calculate the wave length that reduce an intensity by half (-6 dB)
we can use

$$
\begin{align}
I(\theta) &= I_0\ sinc^2(\frac{d\pi}{\lambda}\sin\theta) \\
\frac{1}{2}I_0 &= I_0\ sinc^2(\frac{d\pi}{\lambda}\cdot 1) \\
\frac{1}{2} &= sinc^2(\frac{d\pi}{\lambda}) \\
0.707 &= sinc(\frac{d\pi}{\lambda}) \\
\frac{d}{\lambda} &= 0.443 
\end{align}
$$

reduce an intensity by forth (-12 dB)

$$ \frac{d}{\lambda} = 0.603 $$

