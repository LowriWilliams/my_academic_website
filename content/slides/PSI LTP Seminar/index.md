---
title: Analytical Amplitudes from Numerical Exploration
summary: 
authors: ["Giuseppe De Laurentis"]
tags: [QCD, Scattering Amplitudes, CHY]
categories: []
date: "2019-11-08T00:00:00Z"
markup: blackfriday
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: sky
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---
<html>
	<head>
		<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Indie+Flower">
		<link rel="stylesheet" href="../reveal_custom.css">
	</head>
</html>

{{< slide background-image="PSI-aerialview.jpg" >}}

<br><br>

### <b> Modern Methods for the Computation of Scattering Amplitudes </b>

<br>

Giuseppe De Laurentis

LTP Seminar \
\
<p style="line-height: 0.05;"> <img src="paul-scherrer-institute-psi-logo-vector-transparent.png"; style="max-width:280px;float:center;border:none;">\
\
<font size=2> These slides at [gdelaurentis.github.io/slides/psi-ltp-seminar](/slides/psi-ltp-seminar/#/) </font size> </p>

{{< speaker_note >}}
- Only speaker can read these.
- Press S to view.
{{< /speaker_note >}}

---

<section>
# What are Scattering Amplitudes?

---

<b> S-Matrix and Correlation Functions  </b>

Very conctretly, the LSZ-reduction formula tells us to keep all:

fully-connected, amptuated Feynman diagrams

<img src="ScatteringAmplitudeFeynmanDiagramTransparent.png"; style="max-width:300px;float:center;border:none;margin-top:-5px;">

---

<b> The ''$\sqrt{\textbf{Probability}}$'' of Scattering </b>
<br>

<font size=5>
$$σ_{2 \rightarrow n - 2} = ∑\_{a,b} ∫ dx_a dx_b f\_{a/h_1}(x_a, μ_F) \, f\_{b/h_2}(x_b, μ_F) \;\hat{σ}\_{ab→n-2}(μ_F, μ_R)$$

$$d\hat{σ}\_{n}=\frac{1}{2\hat{s}}dΠ\_{n-2}\;(2π)^4δ^4\big(∑\_{i=1}^n p_i\big)\;|\overline{\mathcal{A}(p_i,μ_F, μ_R)}|^2$$

Better predictions require both more loops and higher multiplicity.

<table width=50% border="1" cellspacing="0" cellpadding="0" style="margin-bottom:-10px">
  <tr class="greenline">
    <td colspan="2", rowspan="2"> <div id="rot90"> <center> <b> $\mathcal{A}_{n-gluons}^{l-loops} \propto g_s^n $ </b> </center> </div> </td>
    <td colspan="4"> <center> multiplicity (n) </center> </td>
  </tr>
  <tr>
    <td><b>4</b></td>
    <td><b>5</b></td>
    <td><b>6</b></td>
    <td><b>7</b></td>
  </tr>
  <tr>
    <td rowspan="3"> <center> loops (l) </center> </td>
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

<!--- <font size=5>Powers of coupling in pure gluon scattering.</font size>  --->

IR singularities have to be cancelled between real and virtual corrections.

More loops $\rightarrow$ analytical complexity; more legs $\rightarrow$ <u> algebraic complexity </u>

</font size>

---

<b> Stripping the Dynamics from the Kinematics </b>
<br>

Color ordering at tree level and one loop <br>
<font size=4> [F.A.Berends, W.Giele](https://pdf.sciencedirectassets.com/271560/1-s2.0-S0550321300X14241/1-s2.0-0550321387906043/main.pdf?X-Amz-Security-Token=AgoJb3JpZ2luX2VjEAIaCXVzLWVhc3QtMSJGMEQCIGNVZuaBsYoWqvtaF%2BAgxc5mpOVy4bMGH2V9AEodTcd4AiAndJhl3k7SA%2Fe2SXVKYCT1Ul4lUrLqXFWVacr%2B1j4YoyraAwhbEAIaDDA1OTAwMzU0Njg2NSIMZCFFK5U%2BuBvoYbtnKrcDAVoIqqSxnZJyWIxHsBuGbbV8ceVrgQ5eYutSzPdHjcMUaIoJlhOXuu2VWIwI6OyG1X3N8KDE816wZTkqwIJT4sU0I7V60zDOZVuZqwDcIom6o5AOm3gPwFYPUE%2B922vgv%2BJT3XwNiqNtjSC00ZFjbectcM7nJa7YWcWAjkZi3oJkIRPvn5m2oOMWET0jR6ZHWhy2jyM7zyiq1oxrXG4JYKB78hua2lVMc3BPdsSombpNeiebjXU4y2Fl35pz8lYIr3Nyws7P91pJS9%2Fzmqjf9QqVHMhjtMWJvQPsYDx%2BJa3UpXT9jo4r1LIERU5%2BZ%2BmVwpqjUqm3jdmvn1p9A3NaxqjyB%2FxfYp6PxAeFmmFi6hlo3IfqGLVoWsTrz0JfNH3L2ADYZhQW8y8QroshqK97GTQqlYbRORZAQeHEILoSjiVDz%2F%2BvT4UupJjaWpECMUca6%2FmrFA3h9KslrYNS%2BxskX0jxleuKkIfdjwoHcES0VA2nq9ELc%2Bhc9Va5T8Wpix7kANcqwOdZtFT5qQSmFOj4e32hzXfefbtqvC4iVBkWMSnvcE4MP3ulM0ac66RuzXZmFnFFzrIHlDDQnozpBTq1AfOoqS7ORld3jyfBg%2FPRvpifiXb3yYmCI1efBvG1zniZHaUld2etzPTcDEWFMm%2FPPAiA5N3c6cL7qQ4xoNuJu6II%2FCVex8l3pxr1LMZxhjcbu24lIRKPxjmN%2BbnMiCCU8VFhR24vzt8cDyKIyUXFIK7qY3OUqcwGDywoER1Ew1y0QvRwtMY8mCBaLbG5oMNSnj7Uf5fQzeKdXs6Dg6fvv4BtNLCR1wFyNDb1T3oNmpT3JEabGG4%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20190708T094930Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTYZF2Y5ZNJ%2F20190708%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=e91db2a858f3b014276b08879802905aaa8b6b99a9a2693fb585b8ada55b9148&hash=0a71e9d7ca1ef201e5ba2b048cea87b8566aa5c71a9df0903d2ea6a86c687cdc&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=0550321387906043&tid=spdf-d25eb1ed-dd86-4e45-80cb-1e3c295697ff&sid=5c9de57e2ed3984ef69997d0bb7d4e65ff39gxrqb&type=client), [Z.Bern, D.A.Kosower](https://pdf.sciencedirectassets.com/271560/1-s2.0-S0550321300X15143/1-s2.0-055032139190567H/main.pdf?X-Amz-Security-Token=AgoJb3JpZ2luX2VjEAIaCXVzLWVhc3QtMSJIMEYCIQD3re8xFPROG2g0iYThs9UNoSNDMKhroRYo0TMSTHZPMwIhAIEVIYT2ghbXJ5W1YvREYQ%2BE8agWUgV1vLbq8nv01II4KtoDCFsQAhoMMDU5MDAzNTQ2ODY1Igysg9ZJldbBrlxNevkqtwOKrvNA%2B8nRTloFiexgu%2FS8oCZHTo4dckrAatSr8SX44XC4V8cbhwOWNQw%2BaUCkYN3vXjUyKd5CUFEAMNKtMKWQL12DhZXgmcLRN7TloRABrIVlY1zx7Q15w0dHkFqBqd%2FaNp4tTbDN5KqTZhiyrgFwU6%2BW7YPlWFqhFqQy215RAsWL4noNHf%2B%2Bq4hA6JXZJJSX%2B%2FLcNRR%2FYyPO%2FBLX%2BD0LYfkSqKz9w7lP29C7%2BWxzQmhyKIXgZOL9hcqp2tEZ55WWSmI6N8wWzXuQYhZ4thP368NFMFd8UN133rnrOhew1xJZcEBIRN50U66TkH7mXduwRFoYB%2BkQqve6I0v9sO4XgEVlSAbhr4LjxZJY%2FlYoFUcIl11EJZDGWkid%2Fm2b%2FB25VT8uvAYSFJ4NM9XUNZmskfeoQ1hGVjRs0hSRsC8PfXFSsS9QumI2MFCKV4w4azjdlkR7N3n8IAGlHQi%2BkZ5T%2B9iUSiTt%2F3znT3pwgg4OCsXTd4oWDNjv6peO50NqGk7k9OxlR0UFhvqTT3nHkzliChGcjrI%2FOo32I%2BAPHcWjsv7qB%2FwPKc4T%2FNlkhPWZKXuJMs5k3xrvMK2ajOkFOrMBkz1BJSpBnB2pM2cVxQZSOVyCbY3SLI8NJBKP7nn3qbav%2Bj%2BqrD1IkW5ZxwaN%2B%2FxGNKrr0YZrOwmZmr7GAoBqLGm17gEFdqfy5%2F6yoMOwFu1upyDVlydHvoxNhRliesqqvxNtoAjNQUF%2FfECJZ1IAhHf7DcnmSTyINrWzVgi%2ByQqiTqSJUQWSQ7%2BJMUy97THP7GuQpNCitwnXIo9PwbNTVixfCiy37rxMAFWwpo%2FLEITtpPs%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20190708T095217Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTYRUVXQZXE%2F20190708%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=35625627d2cae627f9c59d0ea06ec3cf70419b248446a401b304d94cd91a5fd0&hash=b819decaf33c29230d1b66317b3be006fc68534d24f4f0887c6367e38898d15a&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=055032139190567H&tid=spdf-59fd60cb-6bbb-4016-9779-87c46ad6d585&sid=5c9de57e2ed3984ef69997d0bb7d4e65ff39gxrqb&type=client), ... </font size>

<font size=5>$\mathcal{A}^{tree}\_{n}({p_i, λ_i, a_i}) = \; g^{n-2} ∑\_{σ\in S_n/Z_n} \text{Tr}(T^{a_σ(1)}\dots T^{a_σ(n)}) A^{tree}_n(σ(1^{λ_1}),\dots ,σ(n^{λ_n}))$</font size>

<font size=5; style="margin-left:-20px;">
$\mathcal{A}^{1-loop}\_{n}({p\_i, λ\_i, a\_i}) = \; g^{n} ∑\_{σ\in S\_n/Z\_n} N\_{c} \text{Tr}(T^{a\_σ(1)}\dots T^{a\_σ(n)}) A\_{n;1}(σ(1^{λ\_1}),\dots ,σ(n^{λ\_n}))$
</font size>
<font size=5; style="margin-left:-50px;">
$ + ∑\_{c = 2}^{\lfloor n/2 \rfloor + 1}∑\_{σ\in S\_n/Z\_{n;c}} \text{Tr}(T^{a\_σ(1)}\dots T^{a\_σ(c-1)})\text{Tr}(T^{a\_σ( c)}\dots T^{a\_σ(n)}) A\_{n;c}(σ(1^{λ\_1}),\dots ,σ(n^{λ\_n}))$</font size>
</font size>

<br>
Decomposition in terms of basis integrals <br>
<font size=4> [G.'t Hooft, M.Veltman](https://pdf.sciencedirectassets.com/271560/1-s2.0-S0550321300X15684/1-s2.0-0550321379906059/main.pdf?X-Amz-Security-Token=AgoJb3JpZ2luX2VjEAIaCXVzLWVhc3QtMSJGMEQCIGNVZuaBsYoWqvtaF%2BAgxc5mpOVy4bMGH2V9AEodTcd4AiAndJhl3k7SA%2Fe2SXVKYCT1Ul4lUrLqXFWVacr%2B1j4YoyraAwhbEAIaDDA1OTAwMzU0Njg2NSIMZCFFK5U%2BuBvoYbtnKrcDAVoIqqSxnZJyWIxHsBuGbbV8ceVrgQ5eYutSzPdHjcMUaIoJlhOXuu2VWIwI6OyG1X3N8KDE816wZTkqwIJT4sU0I7V60zDOZVuZqwDcIom6o5AOm3gPwFYPUE%2B922vgv%2BJT3XwNiqNtjSC00ZFjbectcM7nJa7YWcWAjkZi3oJkIRPvn5m2oOMWET0jR6ZHWhy2jyM7zyiq1oxrXG4JYKB78hua2lVMc3BPdsSombpNeiebjXU4y2Fl35pz8lYIr3Nyws7P91pJS9%2Fzmqjf9QqVHMhjtMWJvQPsYDx%2BJa3UpXT9jo4r1LIERU5%2BZ%2BmVwpqjUqm3jdmvn1p9A3NaxqjyB%2FxfYp6PxAeFmmFi6hlo3IfqGLVoWsTrz0JfNH3L2ADYZhQW8y8QroshqK97GTQqlYbRORZAQeHEILoSjiVDz%2F%2BvT4UupJjaWpECMUca6%2FmrFA3h9KslrYNS%2BxskX0jxleuKkIfdjwoHcES0VA2nq9ELc%2Bhc9Va5T8Wpix7kANcqwOdZtFT5qQSmFOj4e32hzXfefbtqvC4iVBkWMSnvcE4MP3ulM0ac66RuzXZmFnFFzrIHlDDQnozpBTq1AfOoqS7ORld3jyfBg%2FPRvpifiXb3yYmCI1efBvG1zniZHaUld2etzPTcDEWFMm%2FPPAiA5N3c6cL7qQ4xoNuJu6II%2FCVex8l3pxr1LMZxhjcbu24lIRKPxjmN%2BbnMiCCU8VFhR24vzt8cDyKIyUXFIK7qY3OUqcwGDywoER1Ew1y0QvRwtMY8mCBaLbG5oMNSnj7Uf5fQzeKdXs6Dg6fvv4BtNLCR1wFyNDb1T3oNmpT3JEabGG4%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20190708T100628Z&X-Amz-SignedHeaders=host&X-Amz-Expires=299&X-Amz-Credential=ASIAQ3PHCVTYZF2Y5ZNJ%2F20190708%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=d919ed9ae7a1959e538a14b0201a53f55ff2d050c159575173ea8c207d452dc2&hash=566c1a9bb320be2e7a96e7b9501740e9f7a65fb676b3ea2ba759c1154fa6e5c5&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=0550321379906059&tid=spdf-de178cac-e602-4007-a06a-590f35e6031e&sid=5c9de57e2ed3984ef69997d0bb7d4e65ff39gxrqb&type=client), [Z.Bern, L.Dixon, D.A.Kosower](https://arxiv.org/pdf/hep-ph/9212308.pdf), [R.K.Ellis, G.Zanderighi](https://arxiv.org/pdf/0712.1851.pdf), ... </font size>

<font size=5>
$$A^{1-loop}\_{n;1} = \sum\_i d\_i I^i\_{Box} + \sum\_i c\_i I^i\_{Triangle} + \sum\_i b\_i I^i\_{Bubble} + R$$

<nobr>$A^{tree},\, d\_i,\, c\_i,\, b\_i,$ and $R$ are rational functions of kinematic invariants only.</nobr>

</font size>

---

<b> Intermediate and final expressions  </b>
<br>

Brute force calculations are a mess:

<img src="Five_gluons_mess.png"; style="max-width:500px;float:center;border:none;margin-top:-5px;">

Results are often much easier <br>
<font size=4> [S.J.Parke, T.R.Taylor](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.56.2459),
[F.A.Berends, W.T.Giele](https://reader.elsevier.com/reader/sd/pii/0550321388904427?token=EFDF378B5E170FFAF0B1BECE184A1EB6304F7798C481CF3C0E7D93DF6D367AE0E093D4D4942C932C66E8BEB75DAB41FE) </font size>


<font size=5>

$A^{tree}(1^{+}\_{g}2^{+}\_{g}3^{+}\_{g}4^{-}\_{g}5^{-}\_{g}) = \frac{i\,⟨45⟩^{4}}{⟨12⟩⟨23⟩⟨34⟩⟨45⟩⟨51⟩}$

</font size>

</section>
---
---

<section>
# How do we compute Scattering Amplitudes efficiently?

---

<b> Recursion Relations </b>

test


---

<b> Loops from Trees </b>

test

</section>
---
---

<section>
# Black-Box Interpolation

---

test

</section>
---
---

<section>
# A&nbsp;1.2 &nbsp;Spinor &nbsp;Helicity

---

<b> Lowest-laying representations of the Lorentz group </b>
<br>

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

<b> Spinor Covariants </b>
<br>

Weyl spinors are sufficient for massless particles:

<font size=5>$\text{det}(P^{\dot\alpha\alpha})=m^2 \rightarrow 0 \quad \Longrightarrow \quad P^{\dot\alpha\alpha} = \bar\lambda^{\dot\alpha}\lambda^\alpha$.</font size>

<br>
In terms of 4-momentum components we have:

<font size=5>$$
\lambda\_\alpha=\frac{1}{\sqrt{p^0+p^3}}\begin{pmatrix}p^0+p^3 \\\ p^1+ip^2\end{pmatrix} \, , \;\;\; \lambda^\alpha=\epsilon^{\alpha\beta} \lambda_\beta =\frac{1}{\sqrt{p^0+p^3}}\begin{pmatrix}p^1+ip^2 \\\ -p^0+p^3\end{pmatrix}
$$</font size>

<font size=5>$\bar\lambda\_{\dot\alpha}=\frac{1}{\sqrt{p^0+p^3}}\begin{pmatrix}p^0+p^3 \\\ p^1-ip^2\end{pmatrix} \, , \;\;\; \bar\lambda^{\dot\alpha}=\epsilon^{\dot\alpha\dot\beta}\bar\lambda_{\dot\beta}=\frac{1}{\sqrt{p^0+p^3}}\begin{pmatrix}p^1-ip^2 \\\ \-p^0+p^3\end{pmatrix}$</font size>

<br>

<font size=5>$$
\bar\lambda\_{\dot\alpha} = (\lambda\_\alpha)^* \quad if \quad p^i \in \mathbb{R}; \quad \quad \bar\lambda\_{\dot\alpha} \neq (\lambda\_\alpha)^* \quad if \quad p^i \in \mathbb{C}
$$</font size>

---

<b> Spinor Helicity Invariants </b>
<br>

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

---

<b>Why use complex momenta?</b>

<br>

We want to be able to distinguish between different poles.<br><br>
For example, we want to tell apart:

$$
\frac{1}{⟨ij⟩} \quad and \quad \frac{1}{[ji]}
$$

but with real momenta we would have:

$$
⟨ij⟩ \sim [ji]^* \sim \sqrt{s_{ij}}
$$

</section>
---
---

<section>

<font size=9>
**B. Applications**
</font size>

</section>
---
---
<section>
# 1. Six-Gluon One-Loop Amplitude

---

<b> Brief litterature review </b>

First complete numerical calculation <br>
<font size=5> [R.K.Ellis, W.T.Giele, G.Zanderighi](https://arxiv.org/abs/hep-ph/0602185) </font size>

Pheno applications to 4-jet production <br>
<font size=5> [Z.Bern, G.Diana, L.J.Dixon, F.FebresCordero, S.Hoeche, D.A.Kosower, H.Ita, D.Maitre, K.Ozeren](https://arxiv.org/abs/1112.3940) </font size> <br>
<font size=5> [S.Badger, B.Biedermann, P.Uwer, V.Yundin](https://arxiv.org/abs/1209.0098) </font size>

NMHV analytical cut constructible part <br>
<font size=5> [R.Britto, B.Feng, P.Mastrolia](https://arxiv.org/abs/hep-ph/0602178) </font size>

NMHV analytical rational part <br>
<font size=5> [Z.Xiao, G.Yang, C.Zhu](https://arxiv.org/abs/hep-ph/0607017) </font size>

More litterature info <br>
<font size=5> [David C. Dunbar](https://arxiv.org/abs/0901.1202) </font size>

<!---
<br>
All independent coefficients are available as anchillary files at: [arXiv:1904.04067](https://arxiv.org/abs/1904.04067).

<br>
Our expressions are manifestly rational and gauge invariant.

<br>
For a summary of the litterature see Ref.[15](https://arxiv.org/pdf/0901.1202.pdf). --->
---
<b> Our results </b>

First complete analytical results presented with a single notation.

All expressions are manifestely gauge invariant and rational (no square roots).

Best speed up is a factor of ~75 in the split NMHV configuration <br> (compared to numerical computations in BlackHat).

Worst one is a factor of ~2 in the alternated NMHV configuration.

Bottleneck: numerators of subleading poles.

---

<b> Three mass triangle </b>
<br>

<img src="three_mass_triangle.svg"; width=25%; height=25%; style="float:center;border:none;margin-bottom:0px;">

<font size=5>$\mathcal{D\_{LCD}} = ⟨12⟩[12]⟨34⟩[34]⟨56⟩[56]⟨1|3+4|2]^4⟨3|1+2|4]^4⟨5|1+2|6]^4Δ_{135}^3$</font size>

<!--- An expression was previously obtained in [[16](https://arxiv.org/pdf/hep-ph/0602178.pdf)]. --->

We obtain an explicitly rational expression, like for $\mathcal{N}=1$ SUSY by <br> <font size=5> [N.E.J.Bjerrum-Bohr, D.C.Dunbar, W.B.Perkins](https://arxiv.org/abs/0709.2086). </font size>

---

<b> Pole structure: are there radicals? </b>

<table width=70% border="1" frame="void" cellspacing="0" cellpadding="0">
  <tr class="greenline">
    <td> <center> <img src="Graph5.gv.svg"; style="max-width:360px;float:center;border:none;"> </center> </td>
    <td>
      <center>
        <font size=4>
	Symmetries:<br/>
	  $123456$<br/>
	  $\overline{216543}$<br/>
 	  $345612$<br/>
 	  $\overline{432165}$<br/>
	  $561234$<br/>
	  $\overline{654321}$<br/>
        </font size>
      </center>
    </td>
  </tr>
</table>

<font size=3>

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
      <td>1, 2</td>
      <td>1, 2</td>
      <td>2, 12</td>
      <td>1, 2</td>
      <td>2, 12</td>
      <td>4, 4</td>
      <td>5, 6</td>
      <td>2, 10</td>
      <td>2, 4</td>
    </tr>
    <tr>
      <td colspan="11"> <center> $\dots$ </center> </td>
    </tr>
    <tr>
      <th>⟨3|1+2|4]</th>
      <td>5, 6</td>
      <td>2, 10</td>
      <td>4, 4</td>
      <td>4, 4</td>
      <td>2, 10</td>
      <td>5, 6</td>
      <td>4, 2</td>
      <td>4</td>
      <td>4, 2</td>
      <td style="background:yellow">3.5, 4</td>
    </tr>
    <tr>
      <td colspan="11"> <center> $\dots$ </center> </td>
    </tr>
  </tbody>
</table>

</font size>

---

<b>How to avoid square roots</b>
<br>

All branch cuts should have been taken care of by unitarity cuts.

We should be able to explain this without using square roots.

<br>
The culprit is $\Delta$, which first appears in the <br/> three mass triangle momentum parametrisation:

<font size=5>$\Delta\_{135} = (K\_1 \cdot K\_2)^2 - K\_1^2 K\_2^2$</font size>

<br>
Solution:<br/>
In some limits $\Delta$ behaves like the square of some quantity

<font size=5 style="margin-left:-75px;">$(\Omega\_{351})^2 \equiv (2s\_{12}s\_{56}-(s\_{12}+s\_{56}-s\_{45})s\_{123})^2 = 4s\_{123}^2\Delta\_{135}-4s\_{12}s\_{56}\langle 4|1+2|3]\langle 3|1+2|4]$</font size>

<font size=5>$(\Pi\_{351})^2 \equiv (s\_{123}-s\_{124})^2 = 4\Delta\_{135}-4\langle 4|1+2|3]\langle 3|1+2|4]$</font size>

---

<!--- <iframe src="https://arxiv.org/src/1904.04067v3/anc/AllOneLoop6Gluons/6g_pmpmpm_G/triangle_19_.pdf&embedded=true" style="width:718px; height:700px;" frameborder="0"></iframe> --->

<b> The three-mass triangle rational coefficient </b>

<font size=6>
$$
\begin{gathered}
\scriptscriptstyle \frac{-1/2i⟨23⟩^3[45]^3s\_{123}^2Ω\_{351}}{⟨12⟩[56]⟨1|2+3|4]⟨3|1+2|4]^4⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle \frac{1/4i[12]⟨23⟩^3[45]^3⟨56⟩⟨4|1+2|3]s\_{123}Π\_{351}}{⟨1|2+3|4]⟨3|1+2|4]^3⟨3|1+2|6]Δ\_{135}}+\\\\\\
\scriptscriptstyle \frac{2i⟨23⟩^2[45]^2⟨2|1+3|5]s\_{123}Ω\_{351}}{⟨12⟩[56]⟨1|2+3|4]⟨3|1+2|4]^3⟨3|1+2|6]}+\\\\\\
\dots\\\\\\
\scriptscriptstyle (123456\; \rightarrow \; 345612)+\\\\\\
\scriptscriptstyle (123456\; \rightarrow \; 561234)+\\\\\\
\dots
\end{gathered}
$$
<!-- \scriptscriptstyle \frac{⟨2|3+4|1]⟨6|1+2|5]Ω\_{351}(1i⟨12⟩[12]⟨13⟩[13]\,...⟪4\,\text{terms}⟫...\, -1i⟨23⟩[23]⟨35⟩[35])}{⟨1|3+4|2]⟨3|1+2|4]^2⟨5|1+2|6]Δ\_{135}}+\\\\\\
\scriptscriptstyle \frac{4i⟨12⟩^3[12]^2[13][15]⟨36⟩\,...⟪65\,\text{terms}⟫...\, -4i[12]⟨23⟩^2[23]⟨26⟩[35]⟨36⟩[36]}{⟨1|3+4|2]⟨3|1+2|4]^2⟨5|1+2|6]}+\\\\\\
\scriptscriptstyle \frac{[12]⟨23⟩^3[45]^3⟨56⟩⟨4|1+2|3]^2Π\_{351}(1/8is\_{123}+1/16is\_{124})}{⟨1|2+3|4]⟨3|1+2|4]^2⟨3|1+2|6]Δ\_{135}^2}+\\\\\\
\scriptscriptstyle \frac{-3i⟨23⟩[45]⟨2|1+3|5]^2Ω\_{351}}{⟨12⟩[56]⟨1|2+3|4]⟨3|1+2|4]^2⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle \frac{⟨23⟩\[45\](-4i⟨12⟩^2[12]^2[15]⟨26⟩\,...⟪31\,\text{terms}⟫...\, +4i[12]⟨26⟩^2⟨56⟩[56]^2)}{⟨1|2+3|4]⟨3|1+2|4]^2⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle \frac{5/32i⟨12⟩[12]⟨34⟩[34]⟨56⟩[56]⟨2|3+4|1]⟨4|1+2|3]⟨6|1+2|5]Π\_{351}}{⟨1|3+4|2]⟨3|1+2|4]⟨5|1+2|6]Δ\_{135}^2}+\\\\\\
\scriptscriptstyle \frac{⟨2|3+4|1]⟨4|1+2|3]⟨6|1+2|5]⟨1|3+4|1]⟨56⟩\[56\](-1/4i⟨12⟩[12]⟨23⟩[23]\,...⟪17\,\text{terms}⟫...\, +1/4i⟨24⟩[24]⟨34⟩[34])}{⟨1|3+4|2]⟨3|1+2|4]⟨5|1+2|6]Δ\_{135}^2}+\\\\\\ --->
</font size>
<!---
$$
\begin{gathered}
\scriptscriptstyle \frac{⟨2|3+4|1]⟨4|1+2|3]⟨6|1+2|5]⟨2|3+4|2]⟨56⟩[56](-1/4i⟨12⟩[12]⟨23⟩[23]\,...⟪7\,\text{terms}⟫...\, +1/2i⟨13⟩[14][35]⟨45⟩)}{⟨1|3+4|2]⟨3|1+2|4]⟨5|1+2|6]Δ\_{135}^2}+\\\\\\
\scriptscriptstyle \frac{⟨2|3+4|1]⟨6|1+2|5](7/4i⟨12⟩^2[12]^2[13]⟨14⟩\,...⟪47\,\text{terms}⟫...\, +3/2i⟨23⟩[23]^2⟨25⟩⟨34⟩[35])}{⟨1|3+4|2]⟨3|1+2|4]⟨5|1+2|6]Δ\_{135}}+\\\\\\
\scriptscriptstyle \frac{⟨23⟩^2[45]^2⟨4|1+2|3](5/4i⟨12⟩^2[12]^2[13]⟨14⟩[14]⟨46⟩\,...⟪152\,\text{terms}⟫...\, +5/8i[12]⟨26⟩⟨34⟩[34]⟨36⟩[36]^2⟨46⟩)}{⟨1|2+3|4]⟨3|1+2|4]⟨3|1+2|6]Δ\_{135}^2}+\\\\\\
\scriptscriptstyle \frac{-2i⟨2|1+3|5]^3s\_{123}}{⟨12⟩[56]⟨1|2+3|4]⟨3|1+2|4]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle \frac{3/16i⟨12⟩^2[12]^2⟨14⟩[14][15]⟨24⟩^2[25]⟨26⟩[34]\,...⟪1340\,\text{terms}⟫...\, +3i[13]⟨24⟩^2[24][25]⟨26⟩^4[26]^2[56]}{⟨1|2+3|4]⟨3|1+2|6]Δ\_{135}^2}+\\\\\\
\scriptscriptstyle \frac{-2i⟨24⟩[35]⟨2|1+3|5]^2}{⟨12⟩[56]⟨1|2+3|4]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle (123456\; \rightarrow \; 345612)+\\\\\\
\scriptscriptstyle (123456\; \rightarrow \; 561234)+\\\\\\
\scriptscriptstyle \frac{5/128i⟨12⟩[12]⟨34⟩[34]⟨56⟩[56]⟨2|3+4|1]⟨4|1+2|3]⟨6|1+2|5]Π\_{135}Π\_{351}Π\_{513}}{⟨1|3+4|2]⟨3|1+2|4]⟨5|1+2|6]Δ\_{135}^3}+\\\\\\
\scriptscriptstyle \frac{4i⟨12⟩^4[12]^3⟨13⟩[13][15]\,...⟪680\,\text{terms}⟫...\, +4i⟨23⟩^2[23]^2⟨25⟩⟨34⟩⟨35⟩[35]^2[45]}{⟨1|3+4|2]⟨1|2+3|4]⟨3|1+2|4]⟨3|1+2|6]⟨5|1+2|6]}+\\\\\\
\scriptscriptstyle \frac{-45i⟨12⟩^3[12]^2⟨13⟩[13]^2[23]⟨34⟩\,...⟪1160\,\text{terms}⟫...\, -4i⟨34⟩^2[34]^2⟨35⟩[35]^2⟨45⟩^2[45]}{⟨1|3+4|2]⟨1|2+3|4]⟨3|1+2|6]⟨5|1+6|2]⟨5|1+2|6]}\phantom{+}
\end{gathered}
$$
--->

<font size=5> (Showing ⟨1|3+4|2], ⟨3|1+2|4] and ⟨5|1+2|6] quadruple and triple poles) </font size>

---

<b>A six-gluon one-loop rational part</b>
<br>

<font size=5>
$R^{1-loop}\_6(1^{+}\_{g}2^{-}\_{g}3^{+}\_{g}4^{-}\_{g}5^{+}\_{g}6^{-}\_{g})$
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
which would imply an ansatz with size roughly $10^{10}$.

<!--- An analytical expression for this component was previously obtained in [[18](https://arxiv.org/pdf/hep-ph/0607017.pdf)] from Feynman diagrams. --->
</font size>

---

<b>The pole structure</b>
<br>

is a bit of a mess:

<img src="GraphRational.gv.svg"; style="maxwidth:1000px; float:center; border:none;">

---

<!--- <iframe src="https://arxiv.org/src/1904.04067v3/anc/AllOneLoop6Gluons/6g_pmpmpm_G/rational.pdf&embedded=true" style="width:718px; height:700px;" frameborder="0"></iframe> --->
<b> The rational part </b>

<font size=6>
$$
\begin{gathered}
\scriptscriptstyle\frac{2/3i⟨12⟩^3[15]^3[23]s\_{123}}{[45]⟨1|2+3|1]^2⟨1|2+3|4]⟨1|2+3|6]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle\frac{-2/3i⟨12⟩^3[15]^3[23]⟨3|1+2|5]}{⟨13⟩[45][56]⟨1|2+3|1]^2⟨1|2+3|4]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle\frac{1i⟨12⟩^3[15]^2⟨23⟩[23]^2[56]}{[45]⟨1|2+3|1]⟨1|2+3|4]⟨1|2+3|6]^2⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle(123456\; \rightarrow \; \overline{234561})+
\scriptscriptstyle(123456\; \rightarrow \; 345612)+
\scriptscriptstyle(123456\; \rightarrow \; \overline{456123})+
\scriptscriptstyle(123456\; \rightarrow \; 561234)+
\scriptscriptstyle(123456\; \rightarrow \; \overline{612345})+\\\\\\
\scriptscriptstyle(123456\; \rightarrow \; \overline{654321})+
\scriptscriptstyle(123456\; \rightarrow \; 543216)+
\scriptscriptstyle(123456\; \rightarrow \; \overline{432165})+
\scriptscriptstyle(123456\; \rightarrow \; 321654)+
\scriptscriptstyle(123456\; \rightarrow \; \overline{216543})+
\scriptscriptstyle(123456\; \rightarrow \; 165432)+\\\\\\
\dots
\end{gathered}
$$
</font size>

<!--- 
\scriptscriptstyle\frac{⟨12⟩^2[15]^2\[23\](-1i⟨12⟩[15]+2i⟨23⟩[35])}{[45]⟨1|2+3|1]⟨1|2+3|4]⟨1|2+3|6]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle\frac{1i⟨12⟩^3[15]^2[25]⟨3|1+2|5]}{⟨13⟩^2[45][56]⟨1|2+3|1]⟨1|2+3|4]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle\frac{2i⟨12⟩^2[15]^2[35]⟨3|1+2|5]}{⟨13⟩[45][56]⟨1|2+3|1]⟨1|2+3|4]⟨3|1+2|6]}+\\\\\\
\scriptscriptstyle\frac{-1i⟨12⟩^2[15]⟨23⟩[25]^2⟨2|1+3|5]}{⟨13⟩^2[45][56]⟨1|2+3|4]⟨3|1+2|6]s\_{123}}+\\\\\\
\scriptscriptstyle\frac{-1i⟨12⟩^2[15]^2[25]⟨2|1+3|5]}{⟨13⟩[45][56]⟨1|2+3|4]⟨3|1+2|6]s\_{123}}+\\\\\\
\scriptscriptstyle\frac{⟨24⟩^2⟨26⟩^2(-1/6i⟨13⟩^2[13]⟨46⟩\,...⟪2\,\text{terms}⟫...\, +1/3i[12]⟨14⟩⟨16⟩⟨23⟩)}{⟨12⟩⟨16⟩⟨23⟩⟨34⟩⟨45⟩⟨56⟩⟨1|2+3|4]⟨3|1+2|6]}+\\\\\\ --->

<font size=5> (Showing ⟨1|2+3|1], ⟨1|2+3|6] and symmetric poles)  </font size>

</section>
---
---
<section>
# 2. Five-Parton Two-Loop <br> Finite Remainders

<br>

Preview of refitted results into spinor helicity of <br> <font size=4> [[S. Abreu, J. Dormans, F. Febres Cordero, H. Ita, B. Page, V. Sotnikov](https://arxiv.org/abs/1904.00945)] </font size>

---

<b> Expression complexity </b>

Using the Mandelstam expressions as numerical input, <br> we reconstruct them in spinor helicity.

<img src="LeafCountRatios.png"; style="max-width:560px;float:center;border:none;">

<font size=5>
Showing ratio of leaf counts for Mandelstam and spinor-helicity expressions (x-axis) vs. frequency (y-axis). The complexity is significantly reduced (total leaf count: 4176128 down from 9162373).
.
</font size>

---

<b> Example: uubggg pmpmp Nf1 #3 </b>

<img src="uubggg_pmpmp_nf1_nb3.png"; style="max-width:1024px;float:center;border:none;">

and

<font size=5>
$
-\frac{[32]^3 [41]^3}{2 [31]^3 [42]^3}
$
</font size>

are equivalent.

---

<b> Example: ggggg mpmpp Nf1 # 9 </b>

<img src="ggggg_mpmpp_nf1_9.png"; style="max-width:512px;float:center;border:none;"> <br>
<font size=5> and </font size> <br>
<font size=5>
$-1\frac{[12]³[15][23]⟨25⟩³[35]³}{[13]⁴[25]⟨5|1+2|5]³}+\frac{97}{12}\frac{[12]⁴⟨25⟩[35]⁴}{[13]⁴[25]³⟨5|1+2|5]}$
$+\frac{13}{3}\frac{[12]⁴⟨15⟩[15][35]⁴}{[13]⁴[25]⁴⟨5|1+2|5]}+\frac{1}{4}\frac{[12]⁴⟨15⟩[15]⟨25⟩[35]⁴}{[13]⁴[25]³⟨5|1+2|5]²}$
$-\frac{3}{2}\frac{[12]²⟨25⟩²[25][35]²}{[13]²[25]⟨5|1+2|5]²}+\frac{7}{4}\frac{[12]³⟨25⟩²[35]³}{[13]³[25]⟨5|1+2|5]²}$
$-\frac{43}{3}\frac{[12]³⟨25⟩[35]³}{[13]³[25]²⟨5|1+2|5]}$
$-\frac{25}{3}\frac{[12]³⟨15⟩[15][35]³}{[13]³[25]³⟨5|1+2|5]}$
$-\frac{3}{2}\frac{[12]⟨25⟩[25][35]}{[13][25]⟨5|1+2|5]}$
$+4\frac{[12]²⟨25⟩[35]²}{[13]²[25]⟨5|1+2|5]}$
$-\frac{15}{2}\frac{[12]²[35]²}{[13]²[25]²}$
$+\frac{7}{2}\frac{[12][35]}{[13][25]}$
$-\frac{2}{3}$
</font size>

<font size=5>are equivalent.</font size>

---

<b> Biggest linear systems to solve </b>

Recall that size of the linear system is directly related <br> to the mass dimension of the numerators by [this formula](https://gdelaurentis.github.io/slides/summer-meeting-july2020/#/5/4)

<img src="MaximumMassDimensionComparison.png"; style="max-width:560px;float:center;border:none;">

By performing the partial fraction decomposition before fitting the numerators the size of the biggest systems to solve is significantly reduced.

---

<b> Numerical stability </b>

<img src="RelativeError.png"; style="max-width:700px;float:center;border:none;">
<img src="RelativeErrorTailLogY.png"; style="max-width:700px;float:center;border:none;">

Errors made by double-precision evaluations over $1k$ $collider$ phase space points.

</section>
---
---
<section>
# 3. Higgs + 4-Parton Amplitude <br> (@ finite top-mass) 


---

<b> Example of cut diagram </b>

<img src="HiggsBox.png"; style="max-width:300px;float:center;border:none;">

Only singularity involving $m_{top}$ (from pentagon contributions)

$16 |S\_{1×2×3×4}| = −s\_{12} \, s\_{23} \, s\_{34} \, \langle 1 |2 + 3|4] \, \langle 4|2 + 3|1] + m^2\_{top} \, tr_5(1234)^2$

We can generate point near this singularity in a similar fashion.

---

<b> Structure of the coefficients </b>

The massive external leg (the Higgs) is easily accomodated by considering it as a pair of massless particles (think decay products). <br>
In the end all dependance on $P_{Higgs}$ is removed by using momentum conservation.

The coefficients are Taylor expasions in $m_{top}$:

$C^{(0)} + m^2_{top} C^{(2)}$.

with $C^{(0)}$ and $C^{(2)}$ resabling the six-gluon coefficients.
</section>
---
---
<section>

# 4. Tree Amplitudes from CHY formalism

---

<b> Brief overview </b>

Massless $n-$point tree amplitudes are given by

$\textit{A}\_n \, = \, z\_1^4 \cdot i \sum\_{j = 1}^{(n-3)!} \frac{I\_{\scriptscriptstyle CHY}(z^{(j)}(k); k; ϵ)}{\det(ϕ\_{rst}^{ijk})(z^{(j)}(k); k)}$

The $z's$ are related to the momenta through the scattering equations.

The only process dependant part is $I_{CHY}$, the rest depends only on multiplicity. <br>

For instance:

<font size=5>
$I_{CHY, Einstein Gravity} = PF'(\Psi) \; PF'(\tilde\Psi)$
</font size>

<font size=5>
$I\_{CHY, Yang Mills} = C_n \; PF'(\Psi) \quad \quad I\_{CHY, Biadjoint Scalar} = C_n \; C_n$
</font size>

(See backup slides for specific definitions of functions)

---

<b> Numerical amplitudes</b>

Developed two python packages:

```python
>>> pip install seampy
>>> pip install lips
```

seampy from Scatterin Equations and AMplitudes with PYthon<br>
lips from Lorentz Invarinat Phase Space

Arbitrary-precision floating-point amplitudes with a couple of lines of code

```python
>>> from seampy import theories, NumericalAmplitude
>>> from lips import Particles

>>> theories
[YM, EG, BS, BI, NLSM, Galileon, CG, DF2]

>>> oDF2Amp = NumericalAmplitude(theory="DF2", helconf="+++++")
>>> oParticles = Particles(5)

>>> oDF2Amp(oParticles)
mpc(real='#nbr', imag='#nbr')
```

---

<b> Analytical reconstruction </b>

<font size=5> First complete analytical expressions for $(DF)^2$ theory at five point and more.<br>
For example: </font size>

<font size=4>
$$
\begin{gathered}
    A_{(\text{DF})^2}(1^+,\,2^+,\,3^+,\,4^+,\,5^+) =\\\\\\
    \frac{i[12]⟨13⟩⟨25⟩[35]^2}{⟨12⟩^2⟨34⟩⟨45⟩}+\frac{i[14][24][35]}{⟨12⟩⟨35⟩}+\\\\\\
    (12345 → 23451)\,+\,(12345 → 34512)\,+\\\\\\
    (12345 → 45123)\,+\,(12345 → 51234)\,+\\\\\\
    \frac{2i[15][23]⟨4|1+2|4]}{⟨12⟩⟨34⟩⟨45⟩}+\\\\\\
    \frac{2i[12][45]⟨3|1+5|3]}{⟨15⟩⟨23⟩⟨34⟩}+\\\\\\
    \frac{2i[12][15][34]}{⟨23⟩⟨45⟩}\phantom{+}
\end{gathered}
$$
</font size>

<font size=5> $(DF)^2$ double copies into conformal gravity. </font size>

<font size=4> (CG is the zero-mass limit of a mass deformed theory which reproduces EG at infinite mass) </font size>

</section>
---
---
<section>

# Summary

---
Spinor-helicity rational coefficients can be reconstructed using:

$\circ$ singular limits for to the least common denominator;

$\circ$ doubly singular limits for partial fraction decompositions;

$\circ$ generic ansatze in singular limits for numerators;

<br>

Applications involve tree-level, one-loop and two-loop expressions alike.

It is possible to accomodate masses (both internal/external).

<!---

<br>

2) Amplitudes in the CHY formalism can be computed via:

$\circ$ the scattering equations, numerically solved via elimination theory;

$\circ$ CHY-Integrads, which make manifest relations between theories;

Analytical expressions are then accessible using the above strategy.

---

# Outlook

---

Application to the following quantities is well within reach:

$\circ$ six-parton one-loop amplitudes;

$\circ$ five-parton two-loop amplitudes;

for which we have already reconstructed several components.

<br>

Additionally it might be of interest to:

$\circ$ implement analytical expressions on GPGPU for fast evaluations;

$\circ$ reconstruct the seven-gluon one-loop coefficients;

$\circ$ assemble the NNLO three-jets cross-section;

$\circ$ apply the reconstruction technique to double copy structures.

--->

---

Thank you for your attention!

</section>
---
