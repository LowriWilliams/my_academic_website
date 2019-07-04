---
title: Analytical amplitudes from numerical evaluations
summary: 
authors: ["Giuseppe De Laurentis"]
tags: [QCD, Scattering Amplitudes]
categories: []
date: "2019-02-05T00:00:00Z"
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: sky
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---
<html>
	<head>
		<link rel="stylesheet" href="../reveal_custom.css">
	</head>
</html>

{{< slide background-image="Durham.png" >}}

# Analytical &nbsp; amplitudes &nbsp; from &nbsp; numerical &nbsp; evaluations

<br>
Giuseppe De Laurentis

with Daniel Maitre

<br>
QCD@LHC 2019
<br>

IPPP - Durham University

<img src="IP3_logo_blue.png"; style="max-width:280px;float:center;border:none;"> <img src="DurhamLogo.svg"; style="max-width:280px;float:center;border:none;">

{{< speaker_note >}}
- Only speaker can read these.
- Press S to view.
{{< /speaker_note >}}

---

# Table of Contents

<br>

*1. Motivation and introduction*

*2. Singularity structure*

*3. Ansatz and amplitude reconstruction*

*4. Some results (Yang-Mills in the Standard Model)*

---

<section>

# 1.1 Motivation

---

Cross sections at hadron colliders are given by:

<font size=5>
$σ_{2 \rightarrow n - 2} = ∑\_{a,b} ∫ dx_a dx_b f\_{a/h_1}(x_a, μ_F) \, f\_{b/h_2}(x_b, μ_F) \;\hat{σ}\_{ab→n-2}(μ_F, μ_R)$

$d\hat{σ}\_{n}=\frac{1}{2\hat{s}}dΠ\_{n-2}\;(2π)^4δ^4\big(∑\_{i=1}^n p_i\big)\;|\overline{\mathcal{A}(p_i,μ_F, μ_R)}|^2$
</font size>

<br>

Better predictions require both more loops and higher multiplicity.

<font size=5>

<table width=50% border="1" cellspacing="0" cellpadding="0" style="margin-bottom:-10px">
  <tr class="greenline">
    <td colspan="2", rowspan="2"> <div id="rot90"> <center> <b> $\mathcal{A}_{mult.}^{loops} \propto g_s^n $ </b> </center> </div> </td>
    <td colspan="4"> <center> <b> multiplicity </b> </center> </td>
  </tr>
  <tr>
    <td><b>4</b></td>
    <td><b>5</b></td>
    <td><b>6</b></td>
    <td><b>7</b></td>
  </tr>
  <tr>
    <td rowspan="3"> <b> loops </b> </td>
    <td><b>0</b></td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
  </tr>
  <tr>
    <td><b>1</b></td>
    <td>4</td>
    <td>5</td>
    <td>6</td>
    <td>7</td>
  </tr>
  <tr>
    <td><b>2</b></td>
    <td>6</td>
    <td>7</td>
    <td>8</td>
    <td>9</td>
  </tr>
</table>

</font size>

<font size=5>Powers of coupling in pure gluon scattering.</font size>
 

---

Brute force calculations are a mess:

<img src="Five_gluons_mess.png"; style="max-width:500px;float:center;border:none;margin-top:-5px;">

Results are often much easier [[1](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.56.2459),
[2](https://reader.elsevier.com/reader/sd/pii/0550321388904427?token=EFDF378B5E170FFAF0B1BECE184A1EB6304F7798C481CF3C0E7D93DF6D367AE0E093D4D4942C932C66E8BEB75DAB41FE)]:


<font size=5>

$A^{tree}(1^{+}\_{g}2^{+}\_{g}3^{+}\_{g}4^{-}\_{g}5^{-}\_{g}) = \frac{i\,⟨45⟩^{4}}{⟨12⟩⟨23⟩⟨34⟩⟨45⟩⟨51⟩}$

</font size>

{{< speaker_note >}}
- Can we do the calculation numerically, to bypass the algebraic complexty in the intermediate stages, and directly access the compact analytical final result?
{{< /speaker_note >}}

</section>
---
---

<section>
# 1.2 Color Ordering <br/> <font size=7> and </font size> <br/> master integrals

---

Relation to the full amplitude @ tree level:

<font size=5>$\mathcal{A}^{tree}\_{n}({p_i, λ_i, a_i}) = \; g^{n-2} ∑\_{σ\in S_n/Z_n} \text{Tr}(T^{a_σ(1)}\dots T^{a_σ(n)}) A^{tree}_n(σ(1^{λ_1}),\dots ,σ(n^{λ_n})).$</font size>

<br>
Color decomposition at one loop:

<font size=5; style="margin-left:-20px;">
$\mathcal{A}^{1-loop}\_{n}({p\_i, λ\_i, a\_i}) = \; g^{n} ∑\_{σ\in S\_n/Z\_n} N\_{c} \text{Tr}(T^{a\_σ(1)}\dots T^{a\_σ(n)}) A\_{n;1}(σ(1^{λ\_1}),\dots ,σ(n^{λ\_n}))$
</font size>
<font size=5; style="margin-left:-50px;">
$ + ∑\_{c = 2}^{\lfloor n/2 \rfloor + 1}∑\_{σ\in S\_n/Z\_{n;c}} \text{Tr}(T^{a\_σ(1)}\dots T^{a\_σ(c-1)})\text{Tr}(T^{a\_σ( c)}\dots T^{a\_σ(n)}) A\_{n;c}(σ(1^{λ\_1}),\dots ,σ(n^{λ\_n}))$</font size>
</font size>

<br>
Decomposition in terms of basis integrals:

<font size=5>
$$A^{1-loop}\_{n;1} = \sum\_i d\_i I^i\_{Box} + \sum\_i c\_i I^i\_{Triangle} + \sum\_i b\_i I^i\_{Bubble} + R$$
</font size>

</section>
---
---

<section>
# 1.3 Spinor Helicity

---

The lowest-laying representations of the Lorentz group are:

<font size=5>
(Recall: $\mathfrak{so}(1, 3)_\mathbb{C} \sim \mathfrak{su}(2) \times \mathfrak{su}(2)$)
</font size> 

<font size=5>

| $\boldsymbol{(j\_{-},j\_{+})}$ | dim. | name | quantum field | kinematic variable |
| :-------------: | :-------------: | :------------- | :-------------: | :-------------: |
| (0,0) | 1 | scalar | $h$ | m |
| (0,1/2) | 2 | right-handed Weyl spinor | $\chi_{R\,\alpha}$ | $\lambda_\alpha$ |
| (1/2,0) | 2 | left-handed Weyl spinor | $\chi_L^{\,\dot\alpha}$ | $\bar{\lambda}^{\dot\alpha}$ |
| (1/2,1/2) | 4 | rank-two spinor/four vector | $A^\mu/A^{\dot\alpha\alpha}$ | $P^\mu/P^{\dot\alpha\alpha}$ |
| (1/2,0)$\oplus$(0,1/2) | 4 | bispinor (Dirac spinor) | $\Psi$ | $u, v$ |

</font size>

---

Weyl spinors are sufficient for massless particles:

<font size=5>$\text{det}(P^{\dot\alpha\alpha})=m^2 \rightarrow 0 \quad \Longrightarrow \quad P^{\dot\alpha\alpha} = \bar\lambda^{\dot\alpha}\lambda^\alpha$.</font size>

<br>
In terms of 4-momentum components we have:

<font size=5>

$$
\lambda\_\alpha=\begin{pmatrix}\sqrt{p^0+p^3} \\\ \frac{p^1+ip^2}{\sqrt{p^0+p^3}}\end{pmatrix} \, , \;\;\; \lambda^\alpha=\epsilon^{\alpha\beta} \lambda_\beta =\begin{pmatrix}\frac{p^1+ip^2}{\sqrt{p^0+p^3}} \\\ -\sqrt{p^0+p^3}\end{pmatrix}
$$

$\bar\lambda\_{\dot\alpha}=\begin{pmatrix}\sqrt{p^0+p^3} \\\ \frac{p^1-ip^2}{\sqrt{p^0+p^3}}\end{pmatrix} \, , \;\;\; \bar\lambda^{\dot\alpha}=\epsilon^{\dot\alpha\dot\beta}\bar\lambda_{\dot\beta}=\begin{pmatrix}\frac{p^1-ip^2}{\sqrt{p^0+p^3}} \\\ \-\sqrt{p^0+p^3}\end{pmatrix}$

$ \bar\lambda\_{\dot\alpha} = (\lambda\_\alpha)^\dagger \;\;\; if \;\;\; p^i \in \mathbb{R}$
</font size>

---

Some definitions:

<font size=5>
$$
⟨ij⟩ = λ_iλ_j = (λ_i)^α(λ_j)_α \quad \quad \quad [ij] = \barλ_i\barλ_j = (\barλ_i)\_\dotα(\barλ_j)^\dotα
$$


$$
s_{ij} = ⟨ij⟩[ji]
$$


$$
⟨i\;|\;(j+k)\;|\;l] = (λ_i)^α (\not P_j + \not P_k )\_{α\dotα} \barλ_l^\dotα
$$


$$
⟨i\;|\;(j+k)\;|\;(l+m)\;|\;n⟩ = (λ_i)^α (\not P_j + \not P_k )\_{α \dot α} (\bar{\not P_l} + \bar{\not P_m} )^{\dot α α} (λ_n)_α
$$


$$
tr_5(ijkl) = tr(\gamma^5 \not P_i \not P_j \not P_k \not P_l) =  [i\,|\,j\,|\,k\,|\,l\,|\,i⟩ - ⟨i\,|\,j\,|\,k\,|\,l\,|\,i]
$$

</font size>
</section>
---
---

<section>
# 2.1 Singular limits

---

Singular limits give us information about the poles of the amplitude.

<br>

We need a set of possible poles of the amplitudes:

<font size=5>$r\_i \in \\{ ⟨12⟩, ⟨13⟩, \dots, ⟨1|2+3|4], \dots, s_{123}, \dots \\}$,</font size>

and let $\mathbb{f}$ be the function we want to reconstruct.

<br>

<font size=5>$r\_i \rightarrow ε \ll 1, \quad r\_{j \neq i} \sim \mathcal{O}(1), \quad \mathbb{f} \rightarrow ε^α \; \Rightarrow \; log(\mathbb{f}) \rightarrow α\cdot log(ε)$</font size>

$\Rightarrow$ The slope of $\mathbb{f}(ε)$ in a log-log plot gives us the type of singularity,<br/> if any exists.

---


As an example, let us consider following amplitude:

<font size=5>

$\mathbb{f} = A^{tree}(1^{+}\_{g}2^{+}\_{g}3^{+}\_{g}4^{-}\_{g}5^{-}\_{g}6^{-}\_{g})$

<table width=100% border="1" frame="void" cellspacing="0" cellpadding="0">
  <tr class="greenline">
    <td> <center> $\lim_{⟨12⟩ \rightarrow \epsilon} \mathbb{f} \propto \epsilon^{-1}$ </center> </td>
    <td> <center> $\lim_{⟨13⟩ \rightarrow \epsilon} \mathbb{f} \propto \epsilon^0$ </center> </td>
  </tr>
  <tr>
    <td> <img src="lim12.png"; style="max-width:450px;float:center;border:none;"> </td>
    <td> <img src="lim13.png"; style="max-width:450px;float:center;border:none;"> </td>
  </tr>
</table>

</font size>

---

Studying the rest of the limits yields the least common denominator for $\mathbb{f}$:

$\mathbb{f} = \frac{\mathcal{N\_{LCD}}}{\mathcal{D\_{LCD}}} = \frac{\mathcal{N\_{LCD}}}{⟨12⟩⟨16⟩[16]⟨23⟩⟨34⟩[34][45][56]s\_{234}s\_{345}}$.


<font size=5>

<br>

The complexity of the numerator depends on two parameters:

1. mass dimension; $\quad \quad \quad$ 2. little group scalings.

<br>

<nobr> In this case $\mathcal{N\_{LCD}}$ has mass dimension, phase weights: 10, [-1, 0, -1, 1, 0, 1].</nobr>

The ansatz has 1326 independent terms.

</font size>

</section>
---
---

<section>
# 2.2 Doubly singular limits

---

Except for the easiest cases, we should really think about $\mathbb{f}$ as:

$\mathbb{f} = \sum\_i \frac{\mathcal{N}_i}{\mathcal{D}_i} = \sum\_i \frac{\mathcal{N}_i}{\mathcal{R}_i\mathcal{S}_i}$,

where $\mathcal{R}\_i$ are products of subsets of $\mathcal{D\_{LCD}}$ (i.e. real poles), <br/> and $\mathcal{S}\_i$ are products of factors not in $\mathcal{D_{LCD}}$ (i.e. spurious poles).

<br>

This information can be accessed by studying doubly singular limits:

$r\_i \rightarrow ε \ll 1, \quad r\_j \rightarrow ε \ll 1, \quad \mathbb{f} \rightarrow ε^α \; \Rightarrow \; log(\mathbb{f}) \rightarrow α\cdot log(ε)$

Note: now in general we cannot guarantee $\;r\_{k \neq i, j} \sim \mathcal{O}(1)$


---

Information from taking the doubly singular limits:

<font size=5>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>⟨1|2⟩</th>
      <th>⟨1|6⟩</th>
      <th>[1|6]</th>
      <th>⟨2|3⟩</th>
      <th>⟨3|4⟩</th>
      <th>[3|4]</th>
      <th>[4|5]</th>
      <th>[5|6]</th>
      <th>s_234</th>
      <th>s_345</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>⟨1|2⟩</th>
      <td>1</td>
      <td>1/30</td>
      <td>1/3</td>
      <td>1/31</td>
      <td>1/2</td>
      <td>2/12</td>
      <td>2/3</td>
      <td>2/10</td>
      <td>1/2</td>
      <td>2/10</td>
    </tr>
    <tr>
      <th>⟨1|6⟩</th>
      <td>1/30</td>
      <td>1</td>
      <td>1/2</td>
      <td>1/2</td>
      <td>1/10</td>
      <td>2/4</td>
      <td>2/12</td>
      <td>1/3</td>
      <td>2/10</td>
      <td>2/10</td>
    </tr>
    <tr>
      <th>[1|6]</th>
      <td>1/3</td>
      <td>1/2</td>
      <td>1</td>
      <td>2/12</td>
      <td>2/4</td>
      <td>1/10</td>
      <td>1/2</td>
      <td>1/30</td>
      <td>2/10</td>
      <td>2/10</td>
    </tr>
    <tr>
      <th>⟨2|3⟩</th>
      <td>1/31</td>
      <td>1/2</td>
      <td>2/12</td>
      <td>1</td>
      <td>1/30</td>
      <td>1/3</td>
      <td>2/12</td>
      <td>2/3</td>
      <td>2/10</td>
      <td>1/2</td>
    </tr>
    <tr>
      <td colspan="11"> <center> $\dots$ </center> </td>
    </tr>
  </tbody>
</table>

</font size>

The first number if the slope of the log-log plot in the limit, <br/> the second number is the degeneracy of the phase space in the limit.

<br>
For instance:

$⟨12⟩, ⟨16⟩ \rightarrow \epsilon \quad \Longrightarrow \quad ⟨26⟩, s\_{345}, ⟨2|1+6|5], \dots \rightarrow \epsilon$

---


The slope in the doubly singular limit tells us whether two poles should be in the same denominator and the degeneracy how to separate them.

<font size=5>

<style type="text/css">
    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col0 {
            background:  tomato;
            background:  tomato;
            background:  tomato;
            background:  tomato;
            background:  tomato;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col1 {
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col2 {
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col3 {
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col4 {
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col5 {
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col6 {
            background:  tomato;
            background:  tomato;
            background:  tomato;
            background:  tomato;
            background:  tomato;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col7 {
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
            background:  skyblue;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col8 {
            background:  khaki;
            background:  khaki;
            background:  khaki;
            background:  khaki;
            background:  khaki;
        }    #T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col9 {
            background:  tomato;
            background:  tomato;
            background:  tomato;
            background:  tomato;
            background:  tomato;
        }</style>  
<table id="T_67e20e68_9da2_11e9_b9bf_0242a8af999f" style="margin-top:-30px;" ><caption>Green: forced. Red: forbidden. Blue: optional (at least one). Light blue: optional.</caption> 
<thead>    <tr> 
        <th class="blank level0" ></th> 
        <th class="col_heading level0 col0" >⟨1|2⟩</th> 
        <th class="col_heading level0 col1" >⟨1|6⟩</th> 
        <th class="col_heading level0 col2" >[1|6]</th> 
        <th class="col_heading level0 col3" >⟨2|3⟩</th> 
        <th class="col_heading level0 col4" >⟨3|4⟩</th> 
        <th class="col_heading level0 col5" >[3|4]</th> 
        <th class="col_heading level0 col6" >[4|5]</th> 
        <th class="col_heading level0 col7" >[5|6]</th> 
        <th class="col_heading level0 col8" >s_234</th> 
        <th class="col_heading level0 col9" >s_345</th> 
    </tr></thead> 
<tbody>    <tr> 
        <th id="T_67e20e68_9da2_11e9_b9bf_0242a8af999flevel0_row0" class="row_heading level0 row0" >s_234</th> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col0" class="data row0 col0" >1/2/2</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col1" class="data row0 col1" >2/10/3</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col2" class="data row0 col2" >2/10/3</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col3" class="data row0 col3" >2/10/3</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col4" class="data row0 col4" >2/10/3</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col5" class="data row0 col5" >2/10/4</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col6" class="data row0 col6" >1/2/2</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col7" class="data row0 col7" >2/10/3</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col8" class="data row0 col8" >1</td> 
        <td id="T_67e20e68_9da2_11e9_b9bf_0242a8af999frow0_col9" class="data row0 col9" >1/2/2</td> 
    </tr></tbody> 
</table>

</font size>

<img src="Graph.gv.svg"; style="max-width:720px;float:center;border:none;margin-bottom:-30px;">

<font size=5> Diagramatic representation of relation between poles</font size>

---

Let us briefly consider the coefficient of a three mass triangle:

<img src="three_mass_triangle.svg"; width=25%; height=25%; style="float:center;border:none;margin-bottom:0px;">

$\mathcal{D\_{LCD}} = ⟨12⟩[12]⟨34⟩[34]⟨56⟩[56]⟨1|3+4|2]^4⟨3|1+2|4]^4⟨5|1+2|6]^4Δ_{135}^3$

<font size=4>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>⟨12⟩</th>
      <th>[12]</th>
      <th>⟨34⟩</th>
      <th>[34]</th>
      <th>⟨56⟩</th>
      <th>[56]</th>
      <th>⟨1|3+4|2]</th>
      <th>⟨3|1+2|4]</th>
      <th>⟨5|1+2|6]</th>
      <th>Δ_135</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>⟨1|2⟩</th>
      <td>1</td>
      <td>1/2</td>
      <td>1/2</td>
      <td>2/12</td>
      <td>1/2</td>
      <td>2/12</td>
      <td>4/4</td>
      <td>5/6</td>
      <td>2/10</td>
      <td>2/4</td>
    </tr>
    <tr>
      <td colspan="11"> <center> $\dots$ </center> </td>
    </tr>
    <tr>
      <th>⟨3|1+2|4]</th>
      <td>5/6</td>
      <td>2/10</td>
      <td>4/4</td>
      <td>4/4</td>
      <td>2/10</td>
      <td>5/6</td>
      <td>4/2</td>
      <td>4</td>
      <td>4/2</td>
      <td style="background:yellow">3.5/4</td>
    </tr>
    <tr>
      <td colspan="11"> <center> $\dots$ </center> </td>
    </tr>
  </tbody>
</table>

</font size>

Do we need square roots of momentum invariants?

---

All branch cuts should have been taken care of by unitarity cuts.

We should be able to explain this without using square roots.

<br>
The culprit is $\Delta$, which first appears in the <br/> three mass triangle momentum parametrisation:

<font size=5>$\Delta\_{135} = (K\_1 \cdot K\_2)^2 - K\_1^2 K\_2^2$</font size>

<br>
Solution:<br/>
In some limits $\Delta$ behaves like the square of some quantity

<font size=5 style="margin-left:-50px;">$(\Omega\_{351})^2 \equiv (2s\_{12}s\_{56}-(s\_{12}+s\_{56}-s\_{45})s\_{123})^2 = 4s\_{123}^2\Delta\_{135}-4s\_{12}s\_{56}\langle 4|1+2|3]\langle 3|1+2|4]$</font size>

<font size=5>$(\Pi\_{351})^2 \equiv (s\_{123}-s\_{124})^2 = 4\Delta\_{135}-4\langle 4|1+2|3]\langle 3|1+2|4]$</font size>

</section>
---
---

<section>
# 3.1 Partial fraction decomposition

---

Going back to our tree level example,<br/> let's see how we can group together the pols of the amplitude:

<img src="Graph2.gv.svg"; style="max-width:720px;float:center;border:none;">

---

<img src="Graph3.gv.svg"; style="max-width:720px;float:center;border:none;">

</section>
---
---

<section>
# 3.2 Fitting of ansatz

---

How big is the ansatz?

Easiest to count at constant null phase weights;<br/> the size of the ansatz is a function of:<br/><br/>1. its mass dimension ($d$) $\quad\quad$ 2.  multiplicity of phase space ($m$).

<br>
If we allow only for a polynomial in the numerator, then:<br/><br/> $|s\_{ij}| = \frac{m(m-3)}{2}$ $\quad\quad$ $|tr\_5| = {m-1 \choose 4}$

<br>
$\left(\mkern -9mu \binom{\, |s\_{ij}| \,}{\, d/2 \,} \mkern -9mu \right) \leq$ ansatz size $\leq \left(\mkern -9mu \binom{\, |s\_{ij}| \,}{\, d/2 \,} \mkern -9mu \right) + |tr_5| \left(\mkern -9mu \binom{\, |s\_{ij}| \,}{\, (d-4)/2 \,} \mkern -9mu \right)$

</section>
---
---

<section>
# 4.1 A real application

---

<font size=5>
Let us briefly consider the following quantity:

$R^{1-loop}_6(1^{+}\_{g}2^{-}\_{g}3^{+}\_{g}4^{-}\_{g}5^{+}\_{g}6^{-}\_{g})$
</font size>

<font size=4>
$\mathcal{D\_{LCD}} =$
$⟨12⟩[12]⟨13⟩^2⟨15⟩^2⟨16⟩[16]⟨23⟩[23][24]^2[26]^2⟨34⟩[34]⟨35⟩^2⟨45⟩[45][46]^2⟨56⟩[56]$
$⟨1|2+3|1]^2⟨1|5+6|1]^2⟨1|3+4|2]^2⟨1|2+3|6]^2⟨2|1+6|2]^2⟨2|3+4|2]^2$
$⟨3|1+6|2]^2⟨3|1+2|3]^2⟨3|4+5|3]^2⟨3|1+2|4]^2⟨4|2+3|4]^2⟨4|5+6|4]^2$
$⟨5|1+6|4]^2⟨5|1+6|5]^2⟨5|3+4|5]^2⟨5|1+2|6]^2⟨6|1+2|6]^2⟨6|4+5|6]^2$
$s\_{123}s\_{234}s\_{345}Δ\_{135}^2Δ\_{624}^2$
</font size>

<font size=5>
The mass dimension is now 116,<br/>
which would imply an ansatz with size roughly $10^{10}$
</font size>

---

<img src="GraphRational.gv.svg"; style="maxwidth:1000px; float:center; border:none;">

---

<iframe src="https://arxiv.org/src/1904.04067v3/anc/AllOneLoop6Gluons/6g_pmpmpm_G/rational.pdf&embedded=true" style="width:718px; height:700px;" frameborder="0"></iframe>

</section>
---