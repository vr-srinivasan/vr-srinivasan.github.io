---
title: Points of order 11
date: 2026-05-01
layout: single
mathjax: true
tags: [elliptic curves, modular curves, modular forms, torsion points]
---
In this post, I'll give two proofs that there are no rational points of order \\(11\\) on any elliptic curve over \\(\mathbb{Q}\\). The stuff in this post also appeared in a talk I gave at [STAGE](https://math.mit.edu/nt/old/stage_f23.html) in Fall 2023. These [notes by Tom Weston](https://swc-math.github.io/notes/files/01Weston1.pdf) give a great introduction to the modular curves of level \\(11\\), also with the goal of studying \\(11\\)-torsion points on elliptic curves.
\\(
\newcommand{\x}{\times}
\newcommand{\embed}{\hookrightarrow}
\newcommand{\lra}{\longrightarrow}
\newcommand{\ida}{\mathfrak{a}}
\newcommand{\idm}{\mathfrak{m}}
\newcommand{\idp}{\mathfrak{p}}
\newcommand{\idq}{\mathfrak{q}}
\newcommand{\cO}{\mathcal{O}}
\newcommand{\cF}{\mathcal{F}}
\newcommand{\cG}{\mathcal{G}}
\newcommand{\Z}{\mathbb{Z}}
\newcommand{\Q}{\mathbb{Q}}
\newcommand{\C}{\mathbb{C}}
\newcommand{\F}{\mathbb{F}}
\newcommand{\G}{\mathbb{G}}
\DeclareMathOperator{\Aut}{Aut}
\DeclareMathOperator{\Lie}{Lie}
\DeclareMathOperator{\Gal}{Gal}
\DeclareMathOperator{\Frob}{Frob}
\DeclareMathOperator{\End}{End}
\DeclareMathOperator{\Spec}{Spec}
\DeclareMathOperator{\fppf}{fppf}
\DeclareMathOperator{\nr}{nr}
\DeclareMathOperator{\sm}{sm}
\\)

## The modular curve

Recall the modular curve \\(Y:=Y_1(11)\\) parametrizing elliptic curves with a point of order \\(11\\). It has a canonical compactification \\(X:=X_1(11)\\) which parametrizes generalized elliptic curves. By explicitly counting the possibilities for generalized elliptic in the boundary, one finds that the divisor \\(D := X-Y\\) on \\(X\\) has degree \\(10\\) and that \\(D(\Q)\\) consists of \\(5\\) points (the remaining \\(5\\) points split over \\(\Q(\zeta_{11})\\)). Over \\(\C\\), one knows that the genus \\(g\\) of this curve is computed by the space of weight 2 cusp forms. Since \\(\dim S_2(\Gamma_1(11)) = 1\\), spanned by the modular form
\\[f(z) = \eta(z)^2\eta(11z)^2 = q\prod_{n=1}^\infty (1-q^n)^2(1-q^{11n})^2,\\]
we find that \\(g=1\\), so \\(X\\) is an elliptic curve.

To show that there are no elliptic curves over \\(\Q\\) with a point of order \\(11\\), it suffices to show that \\(Y_1(11)(\Q)=\emptyset\\), or equivalently, that \\(X(\Q) = D(\Q)\\). So in fact it will suffice to show that \\(\\#X(\Q)=5\\).

By computing the Tate normal form of an elliptic curve with a point of order \\(11\\), one can find an explicit Weierstrass equation for \\(X\\); it is given by
\\[X : y^2 + y = x^3-x^2.\\]
Via this equation, we view \\(X\\) as a scheme over \\(\Z\\). We know from moduli considerations that \\(X\\) has good reduction away from \\(11\\), and at \\(11\\) we can see that the reduction is split multiplicative. From the Weierstrass equation for \\(X\\), we compute that the discriminant is \\(-11\\), so in fact the smooth locus \\(X^0\\) of \\(X\\) is the Néron model of \\(X_\Q\\) over \\(\Z\\), and the natural map \\(X^0(\Z)\to X(\Q)\\) is a bijection.

We can explicitly find some rational points
\\[\\{\infty, (0,0), (0,-1), (1,0), (1, -1)\\} \subseteq X(\Q)\\]
and since \\(\\#X(\F_2)=5\\) as well, we in fact conclude that this list of \\(5\\) points enumerates all of the rational torsion points on \\(X\\).

To finish the proof, it will thus suffice to show that \\(X/\Q\\) has Mordell–Weil rank \\(0\\). We will exhibit two methods of doing this; one way will be to use BSD, and the other will be to use a descent argument due to Mazur.

## Method 1: BSD for analytic rank \\(0\\)

By the work of Gross–Zagier and Kolyvagin, to show that \\(X\\) has Mordell–Weil rank 0, it suffices to show that \\(L(f,1)\ne 0\\), where \\(L(f,s)\\) is the complex \\(L\\)-function associated to \\(f\\). Explicitly, one computes the \\(L\\)-function as a Mellin transform to obtain
\\[L(f,1) = \frac{1}{2\pi} \int_0^\infty f(iy)\,dy.\\]
The explicit product expansion for \\(f\\) shows that \\(f(iy)\ge 0\\) for all \\(y\ge 0\\), so in particular we have \\(L(f,1) > 0\\). This approach is probably most efficient for studying \\(11\\)-torsion. Merel’s approach to higher orders actually generalizes this idea to great effect, but it requires extra ingenuity since the modular curve will no longer be elliptic.

## Method 2: Descent via fppf cohomology

Let \\(\cG\\) denote the group scheme \\(X^0[5]\\), which is quasifinite and flat over \\(S := \Spec \Z\\). By definition, \\(\cG\\) fits into an exact sequence of fppf group sheaves
\\[0\lra \cG \lra X^0\overset{[5]}\lra X^0 \lra 0\\]
and so one concludes that we have an injection

\\[X(\Q)/5X(\Q) \cong X^0(\Z)/5X^0(\Z) \embed H^1_\fppf(S,\cG).\\]

So it will suffice to show that \\(H_{\fppf}^1(S,\cG)\cong\Z/5\Z\\). The 5 integral points we already found give rise to an injection \\(\Z/5\Z \embed \cG\\). Let \\(\cF\\) denote the quotient. Away from \\(11\\), we know from the Weil pairing that \\(\cF \cong \mu_5\\). At \\(11\\), the map \\(\Z/5\Z \to \cG\\) is an isomorphism. We conclude that \\(\cF\cong \mu_5^\flat\\) where \\(\mu_5^\flat\\) is the group scheme over \\(S\\) which is obtained from \\(\mu_5\\) by deleting the non-identity points on the fiber at \\(11\\). So \\(\cG\\) fits into an exact sequence
\\[0\lra \Z/5\Z \lra \cG \lra \mu_5^\flat\lra 0.\\]
Now \\(H_\fppf^1(S,\Z/5\Z)=0\\) as there are no nontrivial étale (and hence also no fppf) \\(\Z/5\Z\\)-torsors over \\(S\\), since \\(S\\) is simply connected. So it will suffice to show \\(H^1_\fppf(S,\mu_5^\flat) \cong \Z/5\Z\\).

We observe that \\(\mu_5^\flat\\) by definition fits into an exact sequence of fppf group sheaves

\\[0\lra \mu_5^\flat \lra \mu_5 \lra \iota_*\mu_{5/\F_{11}} \lra 0\\]

where \\(\iota : \Spec \F_{11} \embed S\\) is the inclusion of the closed fiber at \\(11\\). We claim that \\(H_\fppf^1(S,\mu_5) = 0\\). Indeed, the Kummer exact sequence shows that \\(H^1(S,\mu_5) \cong \Z^\x/\Z^{\x 5} = 0\\). So finally we have

\\[H_\fppf^1(S,\mu_5^\flat) \cong H_\fppf^0(S,\iota_*\mu_{5/\F_{11}}) \cong \mu_5(\F_{11}) \cong \Z/5\Z\\]

since \\(\F_{11}\\) contains the \\(5\\)th roots of unity.

So we're done! The generalization of this approach gives Mazur’s original proof for larger torsion orders. 
