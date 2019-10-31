---
title: "Analytical amplitudes from numerical solutions of the scattering equations"
authors:
- admin
date: "2019-10-24"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: ""

abstract: "The CHY formalism for massless scattering provides a cohesive framework for the computation of scattering amplitudes in a variety of theories. It is especially compelling because it elucidates existing relations among theories which are seemingly unrelated in a standard Lagrangian formulation. However, it entails operations that are highly non-trivial to perform analytically, most notably solving the scattering equations. We present a new Python package (seampy) to solve the scattering equations and to compute scattering amplitudes. Both operations are done numerically with high-precision floating-point algebra. Elimination theory is used to obtain general solutions to the scattering equations. These solutions are then applied to a variety of CHY integrands to obtain tree amplitudes for the following theories: Yang-Mills, Einstein gravity, biadjoint scalar, Born-Infeld, non-linear sigma model, Galileon, conformal gravity and (DF)^2. Finally, we exploit this high-precision numerical implementation to explore the singularity structure of the amplitudes and to reconstruct analytical expressions which make manifest their pole structure. Some of the expressions for conformal gravity and the (DF)^2 gauge theory are new to the best of our knowledge."

# Summary. An optional shortened abstract.
summary: 

tags:
- Scattering Amplitudes
- CHY
featured: true

links:
url_pdf: https://arxiv.org/abs/1910.11355

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# image:
#   caption: 'Image credit: [Giuseppe De Laurentis]'
#   focal_point: ""
#   preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
# projects:
# - internal-project

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
# slides: example
---