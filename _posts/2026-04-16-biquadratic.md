---
title: Biquadratic reciprocity
date: 2026-04-16
layout: single
mathjax: true
tags: [elliptic curves, complex multiplication]
---
I’ll tell you how to use the arithmetic of a certain elliptic curve to prove biquadratic reciprocity. I learned this approach from Matt Emerton when I was an undergraduate. At the time I was somewhat confused, though he clearly and patiently explained the ideas to me several times over. I was looking back at the notes I had written down, and I decided to rewrite the argument nicely. 
\\(\newcommand{\x}{\times}
\newcommand{\embed}{\hookrightarrow}
\newcommand{\ida}{\mathfrak{a}}
\newcommand{\idm}{\mathfrak{m}}
\newcommand{\idp}{\mathfrak{p}}
\newcommand{\idq}{\mathfrak{q}}
\newcommand{\cO}{\mathcal{O}}
\newcommand{\cF}{\mathcal{F}}
\newcommand{\Z}{\mathbb{Z}}
\newcommand{\Q}{\mathbb{Q}}
\newcommand{\C}{\mathbb{C}}
\DeclareMathOperator{\Aut}{Aut}
\DeclareMathOperator{\Lie}{Lie}
\DeclareMathOperator{\Gal}{Gal}
\DeclareMathOperator{\Frob}{Frob}
\DeclareMathOperator{\End}{End}
\DeclareMathOperator{\nr}{nr}
\newcommand{\symb}[2]{\left( \frac{\#1}{\#2} \right)_4}\\)

## The curve

Consider the elliptic curve with Weierstrass equation
\\[E:y^2=x^3-x.\\]

The most important property of this curve, for our purposes, is that it admits complex multiplication by \\(\cO:=\Z[i]\\) via the endomorphism
\\[[i](x,y) = (-x,iy)\\]
Though \\(E\\) is defined over \\(\Q\\), the CM is defined over \\(K := \Q(i)\\). We'll view \\(K\subset \C\\), i.e. we will assume we've fixed a complex embedding of \\(K\\) at the outset. With our conventions here, the natural map
\\[\cO \to \End(E_K) \to \End(H^0(E_K,\Omega^1))\cong K\\]
is just the natural inclusion.

## Frobenius elements

Until further notice, we will abuse notation and view \\(E\\) as an elliptic curve over \\(K\\), so that the CM is defined over the field of definition. We will let \\(\gamma = 1+i\\) and \\(\idq = (\gamma)\\) denote the unique ramified prime of \\(\cO\\). From looking at the discriminant, we see that \\(E\\) has good reduction away from \\(\idq\\) (and it's easy to check that it has additive reduction at \\(\idq\\)). Let \\(\idp\\) be a prime of \\(\cO\\) different from \\(\idq\\), and let \\(E_{k(\idp)}\\) denote the reduction of \\(E\\) modulo \\(\idp\\). We have the canonical Frobenius element \\(\Frob_\idp \in \End(E_{k(\idp)})\\), and the Frobenius element is always central in the endomorphism ring. Since the center is identified with \\(\cO = \End(E)\\), we find that there is a canonical element \\(\pi_\idp\in \cO\\) corresponding to \\(\Frob_\idp\\). The isogeny \\(\Frob_\idp\\) has degree \\(\\#k(\idp)=N\idp\\), so \\(\pi_\idp\\) must be a generator of the ideal \\(\idp\\). This, however, only determines \\(\pi_\idp\\) up to unit multiples.

To determine the correct unit multiple, we must be more clever. We can check easily by hand that \\(E[\gamma^3] \subset E(K)\\). Because \\(\Frob_\idp\\) acts trivially on \\(k(\idp)\\)-points, we conclude that \\(\pi_\idp\equiv 1\bmod \gamma^3\\). The natural map \\(\cO^\x\to (\cO/\gamma^3\cO)^\x\\) is an isomorphism, so this uniquely determines \\(\pi_\idp\\). For instance, if \\(p\equiv 3\bmod 4\\) is an inert prime, then \\(\pi_p = -p\\).

## Division fields

This part of the post will more or less apply generally to CM elliptic curves, but we will remain in our specific setup. Fix a prime \\(\idp\\) of \\(\cO\\). Let \\(F=K(E[\idp])\\). The theory of formal groups yields a quick proof of the following proposition, which we leave as an exercise.

<span style="color: #4a90d9;">**Proposition.**</span> The extension \\(F/K\\) is Galois with Galois group \\(k(\idp)^\x\\), is totally ramified at \\(\idp\\), and is unramified away from \\(\gamma \idp\\). If \\(\idp'\\) is the unique prime of \\(F\\) above \\(\idp\\), then the Galois action on the \\(1\\)-dimensional \\(k(\idp)\\)-vector space \\(\idp'/\idp'^2\\) coincides with the natural scaling action of \\(k(\idp)^\x\\).

If \\(\gamma \not \in \idp\\), in fact \\(E\\) acquires good reduction over \\(F\\), which is a very useful fact (and actually applies to non-CM elliptic curves as well). To see this, let \\(L/F\\) denote a field over which \\(E\\) acquires good reduction. Since the inertia group \\(I_{\overline L/L}\\) acts trivially on \\(T_\idp E\\), it follows that the action of \\(I_{\overline L/F}\\) factors through \\(I_{L/F}\\). Also, \\(F\\) contains the \\(\idp\\)-torsion, so the action is trivial after reducing modulo \\(\idp\\). So the action of inertia can be written
\\[\rho : I_{\overline L/F} \twoheadrightarrow I_{L/F} \to \ker\left[\Aut_{\cO_\idp}(T_\idp E) \to \Aut_{k(\idp)}(E[\idp])\right]\cong 1+\idp\cO_\idp \cong \idp\cO_\idp\\]
Such a map must be trivial since it has finite image in a torsion-free group. It follows that in fact the \\(\idp\\)-adic Tate module is unramified over \\(F\\) (not just \\(L\\)!) and so \\(E\\) has good reduction over \\(F\\).

## Biquadratic reciprocity

Given prime elements \\(\alpha,\beta\in \cO\\) coprime to each other and to \\(\gamma\\), we recall the fourth-power symbol \\(\symb{\beta}{\alpha}\in \mu_4 \subset \cO^\x\\) is defined such that
\\[\symb{\beta}{\alpha} \equiv \beta^{\frac{N\alpha - 1}{4}} \bmod \alpha\\]
For any prime \\(\alpha\\), we let \\(\alpha^\* = \symb{-1}{\alpha}\cdot \alpha\\).

<span style="color: #4a90d9;">**Theorem (Biquadratic Reciprocity).**</span> Given primes \\(\alpha,\beta\equiv 1\bmod \gamma^3\\), we have
\\[\symb{\beta}{\alpha} = \symb{\alpha^\*}{\beta}.\\]

We will prove this theorem using the arithmetic of our curve \\(E\\).

We begin by studying the division field \\(L=K(E[-1+2i])\\). Solving explicitly for the torsion, which is easy in this case, one finds that \\(L = K(\sqrt[4]{1-2i})\\) and that \\(L/K\\) is totally ramified at \\(\idq=(\gamma)\\). Let \\(\idq'\\) denote the prime above \\(\idq\\).

---
<span style="color: #4a90d9;">**Lemma.**</span> If \\(\delta \in \cO_\idq\\) satisfies \\(\delta \equiv 1\bmod 4\\), then \\(L_{\idq'}(\sqrt[4]{\delta})/L_{\idq'}\\) is unramified.
<details>
<summary>Proof</summary>
If \(\delta\) is \(1\) or \(1+4i\) modulo \(8\), then already \(K_\idq(\sqrt[4]{\delta})/K_\idq\) is unramified. It will then suffice to check the case that \(\delta = 5\). But in fact, \(L(\sqrt[4]{5}) = L(\zeta_5)\) is indeed unramified over \(L\) above \(\gamma\). \(\square\)
</details>
---
<span style="color: #4a90d9;">**Proposition.**</span> Let \\(\alpha \equiv 1\bmod \gamma^3\\) be a prime. Let \\(F=K(E[\alpha])\\). Then \\(\sqrt[4]{\alpha^\*} \in F\\).

<details>
<summary>Proof</summary>
Sorry about that! Here it is:

Since \(\Gal(F/K)\cong (\cO/\alpha)^\x\), there is a unique \(\Z/4\Z\) subextension, which by Kummer theory must be of the form \(K(\sqrt[4]{\eta})\) for some \(\eta \in K\). Since \(F\) is unramified away from \(\gamma \alpha\), we can write \(\eta = u\gamma^k \alpha^\*\) for some \(u\in \cO^\x\) and \(0\le k\le 3\).

We know that \(L(\sqrt[4]{\eta})/L\) is unramified since \(E\) has good reduction over \(L\). Now since \(\alpha \equiv 1\bmod \gamma^3\), we can check that \(\alpha^\*\) is either \(\equiv 1\bmod 4\) or \(\equiv 1-2i\bmod 4\). Thus \(L(\sqrt[4]{\alpha^\*})/L\) is unramified at \(\idq'\). Taking the compositum of the two extensions, we see that \(L(\sqrt[4]{u\gamma^k})/L\) is unramified at \(\idq'\). This is possible only if \(u=1\) and \(k=0\). QED
</details>
---

With this result in hand, we can complete the proof of biquadratic reciprocity. Let \\(\beta \equiv 1\bmod \gamma^3\\) be another prime. Let \\(\sigma_\beta \in \Gal(F/K)\\) correspond to the endomorphism \\([\beta]\\) of \\(E\\). First, observe that \\(\Frob_\beta = [\beta]\\) as endomorphisms of \\(E_{k(\beta)}\\), so we have

\\[\frac{\sigma_\beta\sqrt[4]{\alpha^\*}}{\sqrt[4]{\alpha^\*}} \equiv (\sqrt[4]{\alpha^\*})^{N\beta-1}\bmod \beta \equiv (\alpha^\*)^{\frac{N\beta-1}{4}} \bmod \beta, \quad \implies \quad \frac{\sigma_\beta\sqrt[4]{\alpha^\*}}{\sqrt[4]{\alpha^\*}} = \symb{\alpha^\*}{\beta}.\\]

To finish the proof, we will compute the LHS in a different way. Let \\(\idp = (\alpha)\\), and let \\(\pi\\) denote a uniformizer for \\(F_{\idp'}\\). Then we can write \\(\sqrt[4]{\alpha^\*} = u\pi^{\frac{N\alpha - 1}{4}}\\) for a unit \\(u\in \cO_{\idp'}^\x\\). Since \\(F_{\idp'}/K_\idp\\) is totally ramified, the Galois group fixes the residue field, so we have
\\[\frac{\sigma_\beta \sqrt[4]{\alpha^\*}}{\sqrt[4]{\alpha^\*}} \equiv \frac{\sigma_\beta (u\pi^{\frac{N\alpha - 1}{4}})}{u\pi^{\frac{N\alpha - 1}{4}}} \equiv \frac{\sigma_\beta \pi^{\frac{N\alpha - 1}{4}}}{\pi^{\frac{N\alpha - 1}{4}}}\equiv \beta^{\frac{N\alpha - 1}{4}} \bmod \pi, \quad \implies \quad \frac{\sigma_\beta \sqrt[4]{\alpha^\*}}{\sqrt[4]{\alpha^\*}} = \symb{\beta}{\alpha}.\\]