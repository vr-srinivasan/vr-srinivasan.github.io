---
title: Projective space is simply connected
date: 2026-04-01
mathjax: true
tags: [algebraic geometry]
---

It is a standard fact in algebraic geometry that the projective space \\(\mathbb{P}^r\\) over any algebraically closed field \\(k\\) is simply connected. When \\(k\\) has characteristic zero, we can work over \\(\mathbb{C}\\) and use a cell decomposition. When \\(k\\) is allowed to have characteristic \\(p\\), one instead needs some algebraic argument, and a number of such arguments can be found [here](https://mathoverflow.net/questions/62282/mathbbpn-is-simply-connected) (I am partial to Emerton's answer among the many interesting answers there).

The point of this post is to give another pretty simple proof I thought of at some point, which, like many of the answers linked above, reduces the case of higher dimensional projective space to just the projective line. 

---

<span style="color: #4a90d9;">**Lemma.**</span> Let \\(V\to X\\) a finite, surjective morphism of irreducible \\(k\\)-varieties, and suppose that for some \\(x\in X(k)\\), the fiber \\(\pi^{-1}(x)\\) consists of a single point. Then \\(\pi_1(V)\to \pi_1(X)\\) is surjective.

<details>
<summary>Proof</summary>

It suffices to show that for \(Y\to X\) a connected finite étale cover of degree \(n\), we have that \(V\times_X Y\) is connected. Let \(\{y_1,\dots,y_n\}\) be the fiber above \(x\). Let \(v\) be the unique point of \(V\) above \(x\). Since \(V\times_X Y\to V\) is finite étale of degree \(n\), the fiber above \(v\) in \(V\times_X Y\) consists of \(n\) points \(\{v_1,\dots,v_n\}\). So each \(y_i\) has a unique preimage in \(V\times_X Y\).

Now \(V\to X\) is finite surjective so every connected component of \(V\times_X Y\) must surject onto \(Y\). But each point \(y_i\) above has only one preimage in \(V\times_X Y\), thus \(V\times_X Y\) can only have one connected component. \(\square\)

</details>

---

To see that \\(\mathbb{P}^r_k\\) is simply connected, we note that \\(\mathbb{P}^r\\) may be realized as the quotient of \\((\mathbb{P}^1)^r\\) by the natural action of the symmetric group \\(\mathfrak{S}_r\\). This action has fixed points along the diagonal. So we can apply the above result to the quotient map \\((\mathbb{P}^1)^r \to \mathbb{P}^r.\\) 


