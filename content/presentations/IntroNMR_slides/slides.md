---
theme: white
bg: "#fff9f0"
#width: 400
url: IntroNMR_slides
port: 4000
#.Page.Store.hasMathJax: true
#.Page.Store.hasTikzJax: true
---

# Introduction
* what is NMR
* what can I use it for ?
* how to use it in practice, i.e. on a Bruker instrument?
* what's the basic principle ?

note:
With this presentation I'd like to get you up to speed with NMR. Focus is on practice.
I'm going to use NMRium, for simplicity.
First, however, I need to introduce a little bit of background and vocabulary, i.e.  'NMR speech'.

---
:::
# a bit of theory
:::
<grid drag="50 90" drop="0 10">
![[spinBoltzmann.jpeg|800]] 
</grid>
<grid drag="50 90" drop="60 10">
A. Atomic nuclei have a quantum property $I$, called spin, which is linked to the magnetic moment though
$\vec \mu=\gamma \vec I$


$I$ can take values in multiples of $\frac{1}{2}$ 
</grid>

---
:::
# a bit of theory
:::
<grid drag="50 90" drop="0 10">
![[spinBoltzmann.jpeg|800]] 
</grid>
<grid drag="50 90" drop="60 10">
B. the magnetic moments will (randomly) arrange on two cones parallel ($\alpha$) and antiparallel ($\beta$) to the external magnetic filed $B_0$.
</grid>
note: 
this at least is the model you'll find in most text books.  It suffers from a couple of defaults, though, and alternative models/representations have been proposed (see, e.g. )

---
:::

:::
<grid drag="90 10" drop="0 10">
The energy of these two (for spin $I=\frac{1}{2}$) states  ($\alpha$ and $\beta$ ) follows the expression

$E=\gamma I B_0$ 
</grid>
<grid drag="50 90" drop="50 10">
The energie difference $\Delta E$ between the two orientations increases thus linearly with increasing field: 
$\Delta E= E_\beta - E_\alpha=\gamma B_0$
</grid>
<grid drag="50 90" drop="0 10">
<svg xmlns="http://www.w3.org/2000/svg" width="194.334" height="333.276" viewBox="-72 -72 145.751 249.957"><g stroke-width=".4" stroke="currentColor" fill="currentColor" stroke-miterlimit="10"><!--path d="M-64.958 174.742H48.853m-113.81-28.453h113.81m-113.81-28.453h113.81m-113.81-28.453h113.81m-113.81-28.452h113.81m-113.81-28.453h113.81M-64.957 4.025h113.81m-113.81-28.453h113.81M-64.957-52.87h113.81m-113.81 230.457V-52.88m28.452 230.467V-52.88m28.453 230.467V-52.88M20.4 177.587V-52.88m28.443 230.467V-52.88m.01 0" fill="none" stroke="gray" stroke-width=".2"></path--><path d="M-64.958 60.93H54.084" fill="none"></path><path d="M52.884 59.33c.1.6 1.2 1.5 1.5 1.6-.3.1-1.4 1-1.5 1.6" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32" name="arrowhead" ></path><g stroke="none"><text y="60.931" x="-64.958" font-family="cmmi10" font-size="10" transform="translate(123.034 2.667)">B</text><text y="62.431" x="-57.373" font-family="cmr7" font-size="7" transform="translate(123.034 2.667)">0</text></g><path d="M-64.958 174.742V-58.111" fill="none"></path><path d="M-66.558-56.91c.6-.1 1.5-1.2 1.6-1.5.1.3 1 1.4 1.6 1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><text y="60.931" x="-64.958" font-family="cmmi10" font-size="10" transform="translate(-3.98 -123.034)" stroke="none">E</text><path d="m-64.958 60.93 85.033-85.032" fill="none"></path><path d="M18.095-24.385c.495.353 1.91.212 2.192.07-.141.283-.283 1.698.07 2.193" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".3199968"></path><text y="60.931" x="-64.958" font-family="cmmi10" font-size="10" transform="translate(88.891 -83.205)" stroke="none">α</text><path d="m-64.958 60.93 85.033 85.034" fill="none"></path><path d="M20.358 143.984c-.354.495-.212 1.909-.07 2.192-.284-.142-1.698-.283-2.193.07" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".3199968"></path><text y="60.931" x="-64.958" font-family="cmmi10" font-size="10" transform="translate(88.891 87.858)" stroke="none">β</text><path d="M-8.052 117.376V4.486" fill="none"></path><path d="M-6.452 116.176c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5M-9.652 5.685c.6-.1 1.5-1.2 1.6-1.5.1.3 1 1.4 1.6 1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><g font-size="10" stroke="none"><text y="60.931" x="-64.958" font-family="cmr10" transform="translate(57.296 -10.81)">Δ</text><text y="60.931" x="-56.625" font-family="cmmi10" transform="translate(57.296 -10.81)">E</text></g></g></svg>

<!--
```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
\draw[very thin,color=gray] (0,-4.1) grid (4,4);
\draw[->] (0,0) -- (4.2,0) node[right] {$B_0$};
\draw[->] (0,-4) -- (0,4.2) node[above] {$E$};
\draw[->] (0,0) -- (3,3) node[right] {$\alpha$};
\draw[->] (0,0) -- (3,-3) node[right] {$\beta$};
\draw[<->] (2,-2) -- (2,2) node[xshift=0.3cm, yshift=-1.5cm] {$\Delta E$};
\end{tikzpicture}
\end{document}
```
-->
</grid>


---
<grid drag="50 90" drop="0 10">
<svg xmlns="http://www.w3.org/2000/svg" width="350.748" height="360.384" viewBox="-72 -72 127.311 136.788"><g stroke-width=".4" stroke="currentColor" fill="currentColor" stroke-miterlimit="10"><path d="M-15.165 56.74h56.906m-56.906-28.453h56.906M-15.165-.165h56.906m-56.906-28.453h56.906m-56.906-28.443h56.906M-15.165 59.586V-57.071M13.288 59.586V-57.071M41.731 59.586V-57.071m.01 0" fill="none" stroke="gray" stroke-width=".2"></path><path d="M-72.07-.165H41.741" fill="none"></path><text y="-.165" x="-15.165" font-family="cmmi10" font-size="10" transform="translate(60.438 1.18)" stroke="none">y</text><path d="M-15.165 56.74V-57.07" fill="none"></path><g stroke="none"><text y="-.165" x="-15.165" font-family="cmmi10" font-size="10" transform="translate(-6.036 -61.938)">B</text><text y="1.335" x="-7.579" font-family="cmr7" font-size="7" transform="translate(-6.036 -61.938)">0</text></g><path d="m-57.844 14.061 85.359-28.453" fill="none"></path><text y="-.165" x="-15.165" font-family="cmmi10" font-size="10" transform="translate(39.821 -6.388)" stroke="none">x</text><path d="M-72.07 56.74 41.416-56.746" fill="none"></path><path d="M39.436-57.028c.495.353 1.909.212 2.192.07-.142.283-.283 1.697.07 2.192" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".3199968"></path><text y="-.165" x="-15.165" font-family="cmmi10" font-size="10" transform="translate(60.438 -54.753)" stroke="none">𝞪</text><path d="M-72.07-57.07 41.416 56.414" fill="none"></path><path d="M41.699 54.435c-.354.495-.213 1.91-.071 2.192-.283-.141-1.697-.283-2.192.07" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".3199968"></path><text y="-.165" x="-15.165" font-family="cmmi10" font-size="10" transform="translate(60.438 59.405)" stroke="none">β</text><path d="M41.741-57.07c0-3.93-25.477-7.114-56.906-7.114-31.428 0-56.905 3.185-56.905 7.113 0 3.929 25.477 7.113 56.905 7.113 31.429 0 56.906-3.184 56.906-7.113Zm-56.906 0" fill="none" stroke-dasharray="3.0,3.0"></path><path d="M-15.165-49.958c-31.428 0-56.905-3.184-56.905-7.113 0-3.928 25.477-7.113 56.905-7.113 31.429 0 56.906 3.185 56.906 6.653" fill="none"></path><path d="M43.341-60.55c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5M43.341-58.73c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><path d="M41.741 56.74c0-3.928-25.477-7.113-56.906-7.113-31.428 0-56.905 3.185-56.905 7.113 0 3.929 25.477 7.113 56.905 7.113 31.429 0 56.906-3.184 56.906-7.113Zm-56.906 0" fill="none" stroke-dasharray="3.0,3.0"></path><path d="M-15.165 63.853c-31.428 0-56.905-3.184-56.905-7.113 0-3.928 25.477-7.113 56.905-7.113 31.429 0 56.906 3.185 56.906 6.653" fill="none"></path><path d="M43.341 53.26c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5M43.341 55.08c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path></g></svg>
<!--
```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
\draw[very thin,color=gray] (-2.1,-2.1) grid (2,2);
\draw[=>] (-2,0) -- (2,0) node[right] {$y$};
\draw[=>] (0,-2) -- (0,2) node[above] {$B_0$};
\draw[=>] (-1.5,-.5) -- (1.5,.5) node[below] {$x$};
\draw[->] (-2,-2) -- (2,2) node[right] {$\alpha$};
\draw[->] (-2,2) -- (2,-2) node[right] {$\beta$};
%\draw[<->] (2,-2) -- (2,2) node[xshift=0.3cm, yshift=-1.5cm] {$\Delta E$};
\draw [, dashed] (0,2) ellipse (2cm and 0.25cm);
\draw [->>](0,1.75) arc
    [
        start angle=270,
        end angle=0,
        x radius=2cm,
        y radius =0.25cm
    ] ;
\draw [, dashed] (0,-2) ellipse (2cm and 0.25cm);
\draw[->>] (0,-2.25) arc
    [
        start angle=270,
        end angle=0,
        x radius=2cm,
        y radius =0.25cm
    ] ;
\end{tikzpicture}
\end{document}
```
-->
</grid>
<grid drag="50 90" drop="50 10">
The spins are distributed randomly amongst the two cones, either in the $\alpha$ or the $\beta$ position, following the Boltzman distribution.
</grid>

note: Although this model is the one you'll find in most textbooks, upon closer inspection it presents a number of issues. Other models exist though.

---
<grid drag="50 90" drop="0 10">
<svg xmlns="http://www.w3.org/2000/svg" width="350.409" height="360.921" viewBox="-72 -72 130.056 137.19"><g stroke-width=".4" stroke="currentColor" fill="currentColor" stroke-miterlimit="10"><path d="M-72.17 56.74H44.486M-72.17 28.287H44.486M-72.17-.165H44.486M-72.17-28.618H44.486M-72.17-57.061H44.486M-69.324 59.586V-57.071m28.452 116.657V-57.071m28.453 116.657V-57.071M16.034 59.586V-57.071M44.476 59.586V-57.071m.01 0" fill="none" stroke="gray" stroke-width=".2"></path><path d="M-69.325-.165H44.486" fill="none"></path><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(60.438 1.18)" stroke="none">y</text><path d="M-12.42 56.74V-57.07" fill="none"></path><g stroke="none"><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(-6.036 -61.938)">B</text><text y="1.335" x="-4.834" font-family="cmr7" font-size="7" transform="translate(-6.036 -61.938)">0</text></g><path d="M-55.098 14.061 30.26-14.392" fill="none"></path><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(39.821 -6.388)" stroke="none">x</text><path d="M-69.325 56.74 44.161-56.746" fill="none"></path><path d="M42.181-57.028c.495.353 1.91.212 2.192.07-.141.283-.283 1.697.071 2.192" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".3199968"></path><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(60.438 -54.753)" stroke="none">𝜶</text><path d="M-69.325-57.07 44.161 56.414" fill="none"></path><path d="M44.444 54.435c-.354.495-.212 1.91-.07 2.192-.284-.141-1.698-.283-2.193.07" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".3199968"></path><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(60.438 59.405)" stroke="none">β</text><path d="M44.486-57.07c0-3.93-25.477-7.114-56.905-7.114-31.429 0-56.906 3.185-56.906 7.113 0 3.929 25.477 7.113 56.906 7.113 31.428 0 56.905-3.184 56.905-7.113Zm-56.905 0" fill="none" stroke-dasharray="3.0,3.0"></path><path d="M-12.42-49.958c-31.428 0-56.905-3.184-56.905-7.113 0-3.928 25.477-7.113 56.906-7.113 31.428 0 56.905 3.185 56.905 6.653" fill="none"></path><path d="M46.086-60.55c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5M46.086-58.73c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><path d="M44.486 56.74c0-3.928-25.477-7.113-56.905-7.113-31.429 0-56.906 3.185-56.906 7.113 0 3.929 25.477 7.113 56.906 7.113 31.428 0 56.905-3.184 56.905-7.113Zm-56.905 0" fill="none" stroke-dasharray="3.0,3.0"></path><path d="M-12.42 63.853c-31.428 0-56.905-3.184-56.905-7.113 0-3.928 25.477-7.113 56.906-7.113 31.428 0 56.905 3.185 56.905 6.653" fill="none"></path><path d="M46.086 53.26c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5M46.086 55.08c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><path d="M-12.42-.165v-56.446" fill="none"></path><path d="M-14.02-55.41c.6-.1 1.5-1.2 1.6-1.5.1.3 1 1.4 1.6 1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><g stroke="none"><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(3.533 -54.239)">M</text><text y="1.335" x="-2.718" font-family="cmmi7" font-size="7" transform="translate(3.533 -54.239)">𝜶</text></g><path d="M-12.42-.165V56.28" fill="none"></path><path d="M-10.82 55.08c-.6.1-1.5 1.2-1.6 1.5-.1-.3-1-1.4-1.6-1.5" fill="none" stroke-linejoin="round" stroke-linecap="round" stroke-width=".32"></path><g stroke="none"><text y="-.165" x="-12.419" font-family="cmmi10" font-size="10" transform="translate(3.533 58.892)">M</text><text y="1.335" x="-2.718" font-family="cmmi7" font-size="7" transform="translate(3.533 58.892)">β</text></g></g></svg>
<!--
```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
\draw[very thin,color=gray] (-2.1,-2.1) grid (2,2);
\draw[->,>=latex] (-2,0) -- (2,0) node[right] {$y$};
\draw[->,>=latex] (0,-2) -- (0,2) node[above] {$B_0$};
\draw[->,>=latex] (-1.5,-.5) -- (1.5,.5) node[below] {$x$};
\draw[->,>=latex] (-2,-2) -- (2,2) node[right] {$\alpha$};
\draw[->,>=latex] (-2,2) -- (2,-2) node[right] {$\beta$};
%\draw[<->] (2,-2) -- (2,2) node[xshift=0.3cm, yshift=-1.5cm] {$\Delta E$};
\draw [, dashed] (0,2) ellipse (2cm and 0.25cm);
\draw [->,>=latex](0,1.75) arc
    [
        start angle=270,
        end angle=0,
        x radius=2cm,
        y radius =0.25cm
    ] ;
\draw [, dashed] (0,-2) ellipse (2cm and 0.25cm);
\draw[->,>=latex] (0,-2.25) arc
    [
        start angle=270,
        end angle=0,
        x radius=2cm,
        y radius =0.25cm
    ] ;
%
\draw[->,>=latex] (0,0) -- (0,2) node[right] {$M_\alpha$};
\draw[->,>=latex] (0,0) -- (0,-2) node[right] {$M_\beta$};
\end{tikzpicture}
\end{document}
```
-->
</grid>
<grid drag="60 90" drop="50 10">
The individual spins on both of the cones are distributed according to the Boltzmann function
$\frac{M_\alpha}{M_\beta}=e^{-\frac{\Delta E}{kT}}$

At the end, the macroscopic magnetization consists only of the, quite small, difference in population between the two energy states.

$M=M_\alpha - M_\beta$
</grid>
---

At equilibrium we will hence be in a situation where there is a (small) macroscopic magnetisation parallel to the external field $B_0$.

```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
\draw[very thin,color=gray] (-2.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (-2,0) -- (2,0) node[right] {$y$};
\draw[->,>=latex] (0,-2) -- (0,2) node[above] {$B_0$};
\draw[->,>=latex] (-1.5,-.5) -- (1.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};
%cones
%\draw[->] (-2,-2) -- (2,2) node[right] {$\alpha$};
%\draw[->] (-2,2) -- (2,-2) node[right] {$\beta$};
%\draw[<->] (2,-2) -- (2,2) node[xshift=0.3cm, yshift=-1.5cm] {$\Delta E$};
%\draw [, dashed] (0,2) ellipse (2cm and 0.25cm);
%\draw [->>](0,1.75) arc
%    [
%        start angle=270,
%        end angle=0,
%        x radius=2cm,
%        y radius =0.25cm
%    ] ;
%\draw [, dashed] (0,-2) ellipse (2cm and 0.25cm);
%\draw[->>] (0,-2.25) arc
%    [
%        start angle=270,
%        end angle=0,
%        x radius=2cm,
%        y radius =0.25cm
%    ] ;
%
\draw[->,>=stealth, line width=1mm] (0,0) -- (0,1.5) node[right] {$M$};
%\draw[->] (0,0) -- (0,-2) node[right] {$M_\beta$};
\end{tikzpicture}
\end{document}
```


---
New, let's apply a magnetic field along the x axis
```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
\draw[very thin,color=gray] (-2.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (-2,0) -- (2,0) node[right] {$y$};
\draw[->,>=latex] (0,-2) -- (0,2) node[above] {$B_0$};
\draw[->,>=latex] (-1.5,-.5) -- (1.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};

\draw[->,>=stealth, line width=1mm] (0,0) -- (0,1.5) node[right] {$M$};
% magnetic B1 field
\draw[->,>=stealth, line width=1mm, blue] (0,0) -- (1.5,0.5) node[right] {$B_1$};

\end{tikzpicture}
\end{document}
```
---
The field $B_1$ will induce a moment on the magnetisation $M$, which will hence rotate:
```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
%\draw[very thin,color=gray] (-2.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (-2,0) -- (2,0) node[right] {$y$};
\draw[->,>=latex] (0,-2) -- (0,2) node[above] {$B_0$};
\draw[->,>=latex] (-1.5,-.5) -- (1.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};

\draw[->,>=stealth, line width=1mm] (0,0) -- (0,1.5) node[right] {$M$};
% magnetic B1 field
\draw[->,>=stealth, line width=1mm, blue] (0,0) -- (1.5,0.5) node[right] {$B_1$};
\draw [->,>=latex](0,1.5) arc
    [
        start angle=90,
        end angle=0,
        x radius =1.5cm,
        y radius =1.5cm
    ] ;
% arrow
\draw[->,>=stealth, red] (3,0) -- (4,0) node[right] {};

% situation after
%\draw[very thin,color=gray] (8.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (5,0) -- (9,0) node[right] {$y$};
\draw[->,>=latex] (7,-2) -- (7,2) node[above] {$B_0$};
\draw[->,>=latex] (5.5,-.5) -- (8.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};

\draw[->,>=stealth, line width=1mm] (7,0) -- (8.5,0) node[right] {$M$};
% magnetic B1 field
\draw[->,>=stealth, line width=1mm, blue] (7,0) -- (8.5,0.5) node[right] {$B_1$};
\draw [->,>=latex](7,1.5) arc
    [
        start angle=90,
        end angle=0,
        x radius =1.5cm,
        y radius =1.5cm
    ] ;
% 2nd arrow
\draw[->,>=stealth, red] (10,0) -- (11,0) node[right] {};

% situation after
%\draw[very thin,color=gray] (8.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (12,0) -- (16,0) node[right] {$y$};
\draw[->,>=latex] (14,-2) -- (14,2) node[above] {$B_0$};
\draw[->,>=latex] (12.5,-.5) -- (15.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};

%
\draw[->,>=stealth, line width=1mm] (14,0) -- (15.5,0) node[below] {$M$};
% magnetic B1 field
%\draw[->,>=stealth, line width=1mm, blue] (14,0) -- (15.5,0.5) node[right] {$B_1$};
%\draw [->,>=latex](14,1.5) arc
%    [
%        start angle=90,
%        end angle=0,
%        x radius =1.5cm,
%        y radius =1.5cm
%    ] ;

\end{tikzpicture}
\end{document}
```
---

Now the spins will evolve under the static magnetic field $B_0$, i.e. precess around it with the *Larmor frequency*:

$\omega= \gamma B_0$

inducing a sinusoidal current in a detection coil:

```tikz
\begin{document}
\begin{tikzpicture}[domain=0:4]
\tikzset{
 declare function={
   fid(\x,\c,\o,\h,\r)={\c*exp(-\x/\r)*cos(\o*\x)+2*\h};
   T=7;
   RFheight=6;
   Aqheight=4;
   plotshift=1.5;
   Tmax=12;
   Tmin=-1;
   infid(\x,\c,\o,\h,\r)={\c/20*exp(\x/\r)*cos(\o*\x)+2*\h};
  }
}
%\draw[very thin,color=gray] (-2.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (-4,0) -- (2,0) node[right] {$y$};
\draw[->,>=latex] (0,-2) -- (0,2) node[above] {$B_0$};
\draw[->,>=latex] (-1.5,-.5) -- (1.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};

\draw[->,>=stealth, line width=1mm] (0,0) -- (1.5,0) node[below] {$M$};
% magnetic B1 field
%\draw[->,>=stealth, line width=1mm, blue] (0,0) -- (1.5,0.5) node[right] {$B_1$};
\draw [->,>=latex](1.5,0) arc
    [
        start angle=0,
        end angle=360,
        x radius =1.5cm,
        y radius =0.5cm
    ] ;
% arrow
\draw[->,>=stealth, red] (3,0) -- (4,0) node[right] {};

% situation after
%\draw[very thin,color=gray] (8.1,-2.1) grid (2,2);
%axes
\draw[->,>=latex] (5,0) -- (9,0) node[right] {$t$};
\draw[->,>=latex] (5,-2) -- (5,2) node[above] {$V$};
%\draw[->,>=latex] (5.5,-.5) -- (8.5,.5) node[xshift=-3.2cm,yshift=-1cm] {$x$};
%\draw[->,>=stealth, line width=1mm] (7,0) -- (8.5,0) node[right] {$M$};
% magnetic B1 field
%\draw[->,>=stealth, line width=1mm, blue] (7,0) -- (8.5,0.5) node[right] {$B_1$};
%\draw [->,>=latex](7,1.5) arc
%    [
%        start angle=90,
%        end angle=0,
%        x radius =1.5cm,
%        y radius =1.5cm
%    ] ;
\draw[scale=0.5,domain=0.01:6,smooth,variable=\x,blue, line width=2pt] plot ({\x+10.3-0.25},{fid(\x*2,2,500,0,10)});
\end{tikzpicture}
\end{document}
```
The signal, called a **Free Induction Decay** attenuates due to what's called *relaxation*.
The oscillations, at the Larmor frequency, depend on the magnetic field the nucleus experiences. The value of the external field is modified due to a number of factors:
* magnetic susceptibility of the material the tube is made of
* magnetic susceptibility of the solution (sample)
* intramolecular factors:
	* shielding by fields induced by the electrons
	* chemical shift anisotropy


--
# longitudinal relaxation ($T_1$)

return to the equilibrium

--

# transverse relaxation ($T_2$)

loss of coherence between individual spins

note: is coherence the right word choice here ?

--

# longitudinal relaxation in the rotating frame ($T_{1\rho}$)

similar to $T_1$ when a Spin-Lock is applied.

___

F

---

<grid drag="60 55" drop="5 10" bg="red">
60 x 55
</grid>

<grid drag="25 55" drop="-5 10" bg="green">
25 x 55
</grid>

<grid drag="90 20" drop="5 -10" bg="gray">
90  x 20
</grid>

---