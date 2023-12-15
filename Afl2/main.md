## KomAn - Opgavesæt B
#### Tim Sehested Poulsen - tpw705


## Opgave 1

### a)
Vi har at både $e^z$ er holomorf på $\mathbb{C}$ og $z^2 +4$ er holomorf på $\mathbb{C} \setminus \{ \pm 2i\}$.
Vi kan så konkludere at $f(z) = \frac{e^z}{z^2 + 4}$ er holomorf på $\mathbb{C} \setminus \{ \pm 2i \}$.
Så giver sætning 4.8 fra [1] at tayolorrækken for $f(z)$ omkring $z_0 = 0$ er konvergent i den største åbne skive omkring 0 som er indehold i $\mathbb{C} \setminus \{ \pm 2i \}$. Det må altså være $K(0,2)$. Så konkluderer vi at $\rho = 2$.

### b)
Det kan umiddelbart ses at $\left(f(z) \cdot (z^2 + 4) \right)^{(n)} = e^z$ da $(e^z)' = e^z$.
Jeg vil starte med at vise at 
$$\left( f(z) \cdot (z^2 + 4) \right)^{(n)} = f^{(n)}(z) \cdot (z^2 + 4) + 2nz f^{(n-1)}(z) + \sum_{j=1}^{n-1} 2j f^{(n-2)}(z)$$
Jeg vil vise det per induktion så for $n=1$ har vi at venstresiden bliver
$$f'(z) \cdot (z^2 + 4) + 2zf(z)$$
og ligeledes bliver højresiden også 
$$f'(z) \cdot (z^2 + 4) + 2zf(z)$$
Så formlen holder for $n=1$. Og antag per induktion at formlen holder for et $n \in \mathbb{N}$, så har vi at
$$\begin{aligned}
&\left( f(z) \cdot (z^2 + 4) \right)^{(n+1)} \\ 
&=\left(f^{(n)}(z) \cdot (z^2 + 4) + 2nz f^{(n-1)}(z) + \sum_{j=1}^{n-1} 2j f^{(n-2)}(z) \right)' \\
&=f^{(n+1)}(z) \cdot (z^2 + 4) + 2zf^{(n)}(z) + 2nz f^{(n)}(z) + 2n f^{(n-1)} + \sum_{j=1}^{n-1} 2j f^{(n-1)}(z) \\
&=f^{(n+1)}(z) \cdot (z^2 + 4) + 2(n+1)z f^{(n)}(z) + \sum_{j=1}^{n} 2j f^{(n-1)}(z)
\end{aligned}$$
hvorfra vi nu kan se at formlen også holder for $n+1$ og derfor har vi vist at formlen holder for alle $n \in \mathbb{N}$.

Jeg bruger nu at $\sum_{j=1}^{n-1} 2j = n(n-1)$ og evaluerer formlen i $z=0$ og får at
$$\begin{aligned}
&f^{(n)}(z) \cdot (z^2 + 4) + 2nz f^{(n-1)}(z) + \sum_{j=1}^{n-1} 2j f^{(n-2)}(z) = e^z \\
\implies
& f^{(n)}(0) \cdot (0^2 + 4) + 2n \cdot 0 \cdot f^{(n-1)}(0) + n(n-1) f^{(n-2)}(0) = e^0 \\
\iff & 4f^{(n)}(0) + n(n-1) f^{(n-2)}(0) = 1 \\
\iff & f^{(n)}(0) = \frac{1}{4} - \frac{n(n-1) f^{(n-2)}(0)}{4} \\
\end{aligned}$$
Vi har så fra sætning 4.8 [1] at $a_k = \frac{f^{(k)}(0)}{k!}$ for taylorrækken med udviklingspunkt 0. Så vi konkluderer at
$$a_k = \frac{\frac{1}{4} - \frac{ k(k-1)f^{(k-2)}(0) }{4}}{k!} 
= \frac{1}{4k!} - \frac{\frac{f^{(k-2)}(0)}{(k-2)!}}{4} = 
\frac{1}{4k!} - \frac{a_{k-2}}{4}$$
hvilket holder for $k\ge2$ og for $k=0,1$ kan man udregne $a_0 = a_1 = \frac{1}{4}$.
For at udregne $f^{(5)}(0)$ skal jeg først udregne $a_3$
$$a_3 = \frac{1}{4\cdot 3!} - \frac{a_1}{4} = \frac{1}{4\cdot 6} - \frac{1}{16} 
=\frac{1}{24} - \frac{1}{16} = - \frac{1}{48}$$

$$f^{(5)}(0) = a_5 \cdot 5! = \frac{5!}{4\cdot 5!} - \frac{a_3\cdot 5!}{4}
= \frac{1}{4} - \frac{-\frac{1}{48} \cdot 120}{4} = \frac{1}{4} + \frac{\frac{5}{2}}{4} = \frac{7}{8}$$

### c)
Jeg started med at omskrive integralet
$$\begin{aligned}
&\frac{1}{2\pi i} \cdot \int_{\partial K(\frac{1}{2}, 1)} \frac{e^z}{z^8 - 4z^6} dz \\
=&\frac{1}{2\pi i} \cdot \int_{\partial K(\frac{1}{2}, 1)} \frac{f(z)}{(z-0)^6} dz
\end{aligned}$$
Herfra bemærker jeg at $\overline{K(\frac{1}{2}, 1)} \subseteq \mathbb{C} \setminus \{ \pm 2i \}$ og at $0 \in K(\frac{1}{2}, 1)$. 
Da kan vi bruge formel $(2)$ fra sætning 4.8 i [1] til at konkludere
$$\frac{1}{2\pi i} \cdot \int_{\partial K(\frac{1}{2}, 1)} \frac{f(z)}{(z-0)^6} = \frac{f^{(5)}(0)}{5!} = \frac{\frac{7}{8}}{120} = \frac{7}{960}$$

## Opgave 2

### a)
Kigger vi på $| f^{(n)}(0) |$ ved brug af sætning 4.8 fra [1] vil vi se at
$$|f^{(n)}(0)| = \left\lvert \frac{n!}{2\pi i} \int_{\partial K(0,r)} \frac{f(z)}{z^{n+1}} dz \right\rvert$$
for ethvert $r > 0$ da $f$ er hel. Bruger vi så sætning 2.8 får vi at 
$$\left\lvert \frac{n!}{2\pi i} \int_{\partial K(0,r)} \frac{f(z)}{z^{n+1}} dz \right\rvert
\le \left\lvert \frac{n!}{2\pi i} \max_{z \in \partial K(0,r)} \frac{f(z)}{z^{n+1}} \cdot 2 \pi \right\rvert
=\le n! \left\lvert \max_{z \in \partial K(0,r)} \frac{f(z)}{z^{n+1}} \right\rvert$$
Det vil være klart at så snart $r \ge 10$ så vil 
$$n! \left\lvert \max_{z \in \partial K(0,r)} \frac{f(z)}{z^{n+1}} \right\rvert
=n! \cdot \frac{\ln(r)^{2023}}{r^{n+1}}$$
og da $r^{n+1}$ "vokser hurtigere" end $\ln(r)^{2023}$ for alle $n \in \mathbb{N}$ vil $\lim_{r \to \infty} \frac{\ln(r)^{2023}}{r^{n+1}} = 0$.
Observerer vi så taylorrækken som givet i sætning 4.8 [1] får vi at
$$f(z) = \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!} (z - 0) ^n = f(0)$$
da hvert led i taylorrækken er 0 for $n \ge 1$.
Så i konklusion får vi at $f(z)$ er konstant for $z \in \mathbb{C}$ da taylorrækken er konvergent for alle $z \in \mathbb{C}$ eftersom $f(z)$ er hel.

## Opgave 3
Da $\Omega$ er et område er det altså åbent. Da må vi for hvert $z_0 \in \Omega$ kunne konstruere en kugle $K(z_0, r_0)$ således at $K(z_0, r_0) \subseteq \Omega$. Denne kugle er enkelt sammenhængende vi har fra sætning 4.10 [1] at der eksisterer en $f \in \mathcal{H}(K(z_0,r_0))$ så $\mathcal{R}f = u$.
Vi kan da bruge korollar 3.9 til at sige
$$f(z_0) = \frac{1}{2\pi} \int_{0}^{2\pi} f(z_0 + re^{it}) dt$$
for ethvert $0 \le r < r_0$. Vi ved per definition af integraler af komplekse funktioner at 
$$\frac{1}{2\pi} \int_{0}^{2\pi} f(z_0 + re^{it}) dt
=\frac{1}{2\pi} \int_{0}^{2\pi} \mathcal{R}f(z_0 + re^{it}) dt
+ i\frac{1}{2\pi} \int_{0}^{2\pi} \mathcal{C}f(z_0 + re^{it}) dt$$
Da $\mathcal{R}f = u$ observerer vi da at
$$u(z_0) = \mathcal{R}f(z_0) =
\frac{1}{2\pi} \int_{0}^{2\pi} \mathcal{R}f(z_0 + re^{it}) dt
= \frac{1}{2\pi} \int_{0}^{2\pi} u(z_0 + re^{it}) dt$$
for alle $0 \le r < r_0$. Hvilket givet det ønskede resultat.


### a)

### b)
Lad $r_0 > 0$ være givet som fra forrige opgave. Altså at for $z_0$ (hvor der er lokalt maksimum) har vi
$$u(z_0) = \frac{1}{2\pi} \int_{0}^{2\pi} u(z_0 + r e^{it}) dt$$
så længe $0 < r < r_0$. Jeg kan omskrive dette til
$$\begin{aligned}
&u(z_0) = \frac{1}{2\pi} \int_{0}^{2\pi} u(z_0 + r e^{it}) dt \\
\iff&0 = \frac{1}{2\pi} \int_{0}^{2\pi} u(z_0 + r e^{it}) - u(z_0) dt \\
\iff&0 = \frac{1}{2\pi} \int_{0}^{2\pi} u(z_0 + r e^{it}) - \frac{1}{2\pi} \int_0^{2\pi}u(z_0) dt \\
\iff&0 = \int_{0}^{2\pi} u(z_0 + r e^{it}) - u(z_0) dt \\
\end{aligned}$$
Lad nu $u(z_0)$ være et maksimum i kuglen $K(z_0, r_1)$ så vil vi have at for alle $r < \min(r_0, r_1)$ vil vi have at $u(z_0 + re^{i t}) \le u(z_0)$ for alle $t \in \mathbb{R}$.
Altså er $u(z_0 + re^{it}) - u(z_0) \le 0$ og hvis integralet af denne funktion skal være $0$ mens den aldrig er positiv og samtidig med at den er kontinuert (da u(z) er det), kan vi konkludere at $u(z_0 + re^{it}) - u(z_0) = 0$ for alle $t \in \mathbb{R}$ og $0 < r < \min(r_0, r_1)$.
Det giver os at $u(z) = u(z_0)$ for $z \in K(z_0, \min(r_0, r_1))$ og altså er $u(z)$ konstant i kugle omkring $z_0$.

## Referencer
[1] Christian Berg, Complex Analysis. Lecture Notes, 2016, ISBN 9 788770 786195,