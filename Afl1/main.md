## KomAn - Opgavesæt A
#### Tim Sehested Poulsen - tpw705


## Opgave 1

### a)
Det ses rimelig hurtigt på figuren at billedkurven går i gennem punktet $1$ præcist da kurven skærer x-aksen. Samtidig ligner det at kurver går mod punktet $0$, men det kan ikke ses på figuren om den faktisk rammer punktet, og hvis man ved at $e^z$ ikke har nogle $0$ punkter så kan man konkludere at den ikke rammer punktet $0$.


### b)
Jeg kan ved brug af sætning 1.18 [1] konkludere at


$$\begin{aligned}
&f(z) - 1 = 0 \\
\iff &e^{-z^2/2} = 1 \\
\iff &\frac{-z^2}{2} = 2\pi i k, \text{ for } k \in \mathbb{Z} \\
\iff & z^2 = -4\pi i k, \text{ for } k \in \mathbb{Z}
\end{aligned}$$

Det kan let ses at $|-4\pi i k| = 4\pi |k|$ og 
$$\arg(-4\pi i k) =
\begin{cases}
 \frac{3\pi}{2} &\text{ k > 0 } \\
\frac{\pi}{2} & \text{ k < 0} \\
0 & \text{ k = 0}
\end{cases}$$

Da må vi kunne konkludere at 

$$z =
\begin{cases}
\pm \sqrt{4\pi k} \cdot \left(\cos(\frac{3\pi}{4}) + i \sin(\frac{3\pi}{4}) \right) & \text{hvis k > 0}\\
\pm \sqrt{4\pi k} \cdot \left(\cos(\frac{\pi}{4}) + i \sin(\frac{\pi}{4}) \right) & \text{hvis k < 0}\ \\
0 & \text{hvis k = 0}
\end{cases}$$
Hvilket udgør samtlige nulpunkter til $f(z) - 1$.

### c)
Betragter vi funktionen $g(z) = -z^2/2$, vil vi kunne observere at for ethvert punkt $(a + ib) \in \mathbb{C}$ med $a,b \in \mathbb{R}$ at 


$$\begin{aligned}
&g(z) = a+ib \\
\iff &-z^2/2 = a+ib \\
\iff &z^2 = -2(a+ib) \\
\end{aligned}$$

Antag at $r = |a+ib|$, så har ved brug af løsningen til opgave S.1.(f) fra supplerende opgaver har vi at 

$$\begin{aligned}
z=
\begin{cases}
    \pm \left( \sqrt{r + a} + i\sqrt{r-a} \right) & \text{ hvis b > 0 } \\
    \pm \left( \sqrt{r+a} - i\sqrt{r-a} \right) & \text{ hvis b < 0} \\
\end{cases}
\end{aligned}$$


I begge disse tilfælde vil der være 2 løsninger, men det vil også være sådan at vi i begge har at en af løsningerne har $\mathcal{R}(z) < 0$ hvilket så udelukkes. Altså er der kun 1 løsning til $\frac{-z^2}{2} = a+ib$ så længe den reelle del skal være positiv.
Da må vi kunne konkludere at $g(z)$ er injektiv på det højre halvplan.
Kigger vi så på normen $|\frac{-z^2}{2}|$ for $z \in \Omega_{\sqrt{2\pi}}$ ser vi

$$|\frac{-z^2}{2}| = \frac{1}{2}|z^2| \le \frac{1}{2}\sqrt{2\pi}^2 = \pi$$

Specielt må det betyde at $|\mathcal{C}(g(z))| \le \pi$ for $z \in \Omega_{\sqrt{2\pi}}$.
Kigger vi så på $g(z_1) = a + ib$ og $g(z_2) = c+id$ for $z_1, z_2 \in \Omega_{\sqrt{2\pi}}$ hvorom det gælder at $a,b,c,d \in \mathbb{R}$ og vi antager at $f(z_1) = f_(z_2)$ vil vi se at

$$e^{g(z_1)} = e^{g(z_2)} \iff e^a e^{ib} = e^c e^{id}$$

Hvor vi herfra kan konkludere at $|f(z_1)| = e^a = |f(z_2)| = e^c$ og kan derfor fjerne dem på begge sider af ligheden.
Til slut kan vi så løse følgende med brug af sætning 1.18

$$ e^{ib - id} = 1 \iff i(b - d) = 2\pi i p \iff b = 2\pi p + d$$

for alle $p \in \mathbb{Z}$. Men da vi lige har kunne konkludere at $|\mathcal{C}(g(z_1))|,| \mathcal{C}(g(z_2))| \le \pi$ må $b,d \le \pi$ og vi har da kun tilbage at $p=0$ er en løsning og derfor er $b = d$ og vi kan så konkludere at $f(z_1) = f(z_2)$ giver at $g(z_1) = g(z_2)$ som vi lige har vist er injektiv altså er $z_1 = z_2$ og $f$ er injektiv.


## Opgave 2
### a)
Starter vi med at observere den geometriske række og differentierer den 2 gange får vi at

$$\begin{aligned}
&\left( \sum_{n = 0}^{\infty} z^n \right) '' = \left( \frac{1}{1 - z}\right)'' \\
&\left( \sum_{n = 0}^{\infty} (n+1) z^n \right) ' = \left( \frac{1}{(1 - z)^2}\right)' \\
& \sum_{n = 0}^{\infty} (n+2)(n+1) z^n  = \frac{2}{(1 - z)^3} \\
\end{aligned}$$

Hvor denne række vil have samme konvergensradius per 4.23 i [2], hvilket er $\rho_f = 1$ da den geometriske række har konvergensradius $1$.
Jeg kan nu multiplicere med $z^2$ og bevare konvergensradius ifølge 4.15 i [2]. Jeg får at

$$\sum_{n=2}^{\infty} n(n-1)z^n = \frac{2z^2}{(1-z)^3}$$
$$\implies \sum_{n=0}^{\infty} n(n-1)z^n = \frac{2z^2}{(1-z)^3}$$

Hvor implikationen kommer fra at de første 2 led er $0$.
Altså har vi vist det ønskede.

### b)
Jeg definerer først mængden $A = \{k! | k \in \mathbb{N} \}$. Jeg kan dernæst betragte følgen
$a_0 := 0$ og dernæst $a_n := 1_A(n)$ for $n \in \mathbb{N}$. Da vil det være sådan at

$$\sum_{n = 1}^{\infty} z^{n!} = \sum_{n=0}^{\infty} a_n z^n$$

Kigger vi på mængden $T_h = \{ t \ge 0 | \{|a_n| t^n\}_{n \in \mathbb{N}_0} \text{ er en begrænset følge} \}$.
Da $a_n$ kun antager værdierne $1$ og $0$ kan vi se at $a_n t^n \le t^n$, hvilket udgør en konvergent følge så længe $t \le 1$.
Ligeledes vil følgen $\{a_n t^n\}_{n \in \mathbb{N}_0}$ divergere for $t > 1$ så derfor må $\sup T_h = 1$. Derfra kan vi konkludere at $h(z)$ har konvergensradius $\rho_h = 1$.
Vi bemærker også at $\lim_{n \to \infty} \sqrt[n]{|a_n|}n$ ikke eksisterer da $a_n$ enten er $1$ eller $0$ og $\sqrt[n]{1} = 1$ og $\sqrt[n]{0}=0$ giver at følgen divergerer da den skifter mellem 0 og 1.


## Opgave 3
### a)
Jeg vil først vise at $f$ er injektiv. Antag at $f(z_1) = f(z_2)$ så har vi altså at

$$\begin{aligned}
&\frac{z_1 + 2}{z_1 - i} = \frac{z_2 + 2}{z_2 - i} \\
\iff & (z_1 + 2)(z_2 - i) = (z_2 + 2)(z_1 -i) \\
\iff & z_1z_2 - iz_1 + 2z_2 -2i = z_2z_1 -iz_2 + 2z_1 -2i \\
\iff &  - iz_1 + 2z_2 = -iz_2 + 2z_1  \\
\iff & z_2 (2 + i) = z_1 (2 +i)  \\
\iff & z_2  = z_1   \\
\end{aligned}$$

Altså er $f$ injektiv. Vi kan se at $f$ er surjektiv ved at se at for et arbitrært $w \in \mathbb{C}$ kan vi løse ligningen $f(z) = w$ og få at

$$\begin{aligned}
&\frac{z + 2}{z - i} = w \\
\iff &z + 2 = wz - wi \\
\iff &z(1-w) = -2 - wi \\
\iff &z = \frac{-2 - wi}{1-w}
\end{aligned}$$

Hvilket altid er veldefineret da $w \neq 1$ per definition af $f$. Altså er $f$ surjektiv og injektiv, og
den inverse til $f$ er givet ved

$$f^{-1}(w) = \frac{-2 - wi}{1-w}$$

### b)
For begge kurver kan vi observere at $\gamma_1(0) = \gamma_2(0) = 0$ og da vil $f(\gamma_1(0)) = f(\gamma_2(0)) = \frac{2}{-i} = 2i$. Altså skærer de 2 billedkurver hinanden i punktet $2i$.
Da $f$ er sammensat af $z + 2$ og $z - i$ hvilket begge er holomorfe funktioner og per 1.3 i [1] må $f$ også være holomorf da den er defineret for $z \in \mathbb{C} \setminus \{i\}$.
Eftersom $\gamma_1$ og $\gamma_2$ er differentiable kurver med afledte $\gamma_1'(t) = 1$ og $\gamma_2'(t) = i$ for alle $t \in \mathbb{R}$ kan vi se at kurvernes skæringsvinkel for $t=0$ er vinklem mellm $\gamma_1'(0)$ og $\gamma_2'(0)$ som er $\frac{\pi}{2}$. Fra s. 16 i [1] har vi da givet at skæringsvinklen mellem billedkurverne er den samme som for kurverne selv, altså er skæringsvinklen mellem billedkurverne også $\frac{\pi}{2}$.


## Referencer
[1] Christian Berg, Complex Analysis. Lecture Notes, 2016, ISBN 9 788770 786195,

[2] Analyse 1 af Matthias Christiandl, 4. udgave ved Søren Eilers og Henrik Schlichtkrull
