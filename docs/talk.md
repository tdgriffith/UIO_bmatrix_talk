<!-- .slide: data-background="#500000" class="dark" -->

# An Unknown B Matrix with Unknown Inputs

## T. Griffith
#### Quantum Seminar

#### July 09, 2021

---

<!-- .slide: data-background="#ffffff" class="light" -->

# 1. UIO Recap
# 2. Optimization of Linear Systems
# 3. Identifying the "Best Fit" B Matrix for the Brain
# 4. Application to Emotion Data
# 5. Application to Movement Data
# 6. Perterbations

---

<!-- .slide: data-background="#ffffff" class="light" -->

# UIO Review: Estimator Architecture


<img class="plain" src="assets/adapt_est.png" alt="Trial 5, Averaged" width="50%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

# A Polynomial Basis

{$1,x,x^2,x^3,\ldots,x^n$}

$1+2t+0.5t^2$

<img class="plain" src="assets/poly_basis.png" alt="Trial 5, Averaged" width="50%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

# Polynomial Basis Comparison: Fourier 1-300 hz


<img class="plain" src="assets/fourier_EEG.png" alt="Trial 5, Averaged" width="75%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

# Polynomial Basis Comparison: 1-6th 


<img class="plain" src="assets/poly_EEG.png" alt="Trial 5, Averaged" width="75%">


---


<!-- .slide: data-background="#ffffff" class="light" -->

# Some Obscured Assumptions

- $B=I$
 - $\dot{x}=Ax+Bu$
- SIMO 

---

<!-- .slide: data-background="#ffffff" class="light" -->

# A Better B Matrix?
- Alter B to improve modeling error $e_y$
 - Convex Optimization

---

<!-- .slide: data-background="#ffffff" class="light" -->

# Convex Optimization
an optimization problem in which the objective function is a ***convex function*** and the feasible set is a ***convex set***

---

<!-- .slide: data-background="#ffffff" class="light" -->

# the objective function is a ***convex function***
<img class="plain" src="assets/convex_function_ex.png" alt="Trial 5, Averaged" width="75%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

# the feasible set is a ***convex set***
<img class="plain" src="assets/convex_set.png" alt="Trial 5, Averaged" width="40%">
<img class="plain" src="assets/not_convex_set.png" alt="Trial 5, Averaged" width="40%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

# Important Properties of Convex Problems
- every local minimum is a global minimum
- gradient descent converges in polynomial time

---

<!-- .slide: data-background="#ffffff" class="light" -->

# *A* Convex Function for B matrix optimization
- $\min ||y-\hat{y}-C \Delta B \hat{u}||_2$
- ***not*** the only possible minimization

---

<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix Optimization Example
- $\min ||y-\hat{y}-C \Delta B \hat{u}||_2$
- $B=\begin{bmatrix} 1.2 \\\ 1 \\\ 1.6 \end{bmatrix}$, $B_m=\begin{bmatrix} 1 \\\ 1 \\\ 1 \end{bmatrix}$
- $\Delta B=\begin{bmatrix} 0.18 \\\ 0 \\\ 0.37 \end{bmatrix}$, $B_f=\begin{bmatrix} 1.18 \\\ 1 \\\ 1.37 \end{bmatrix}$

---

<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix Optimization Example
- $\min ||y-\hat{y}-C \Delta B \hat{u}||_2$
<img class="plain" src="assets/toy_Bopt2.png" alt="Trial 5, Averaged" width="90%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix on EEG Data
<img class="plain" src="assets/Bopt.png" alt="Trial 5, Averaged" width="90%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix on EEG Data
<img class="plain" src="assets/B_ic.jpg" alt="Trial 5, Averaged" width="70%">


---


<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix Maps
<img class="plain" src="assets/UIO_opt.jpg" alt="Trial 5, Averaged" width="45%">
<img class="plain" src="assets/Bmap2.png" alt="Trial 5, Averaged" width="45%">


---



<!-- .slide: data-background="#ffffff" class="light" -->
<section>

<h2> B Matrix on EEG Data: ***Satisfaction*** </h2>
<img class="plain" src="assets/sat_map.png" alt="Trial 5, Averaged" width="60%">

</section>

<section>

<img class="plain" src="assets/sat_avg.png" alt="Trial 5, Averaged" width="60%">

</section>

---

<!-- .slide: data-background="#ffffff" class="light" -->

<section>
<h2> B Matrix on EEG Data: ***Surprise*** </h2>

<img class="plain" src="assets/surp_map.png" alt="Trial 5, Averaged" width="60%">

</section>

<section>

<img class="plain" src="assets/surp_avg.png" alt="Trial 5, Averaged" width="60%">

</section>

---

<!-- .slide: data-background="#ffffff" class="light" -->

<h2> B Matrix on EEG Data: ***Fear*** </h2>
<section>
<img class="plain" src="assets/fear_map.png" alt="Trial 5, Averaged" width="60%">

</section>

<section>

<img class="plain" src="assets/fear_avg.png" alt="Trial 5, Averaged" width="60%">

</section>

---

<!-- .slide: data-background="#ffffff" class="light" -->
<section>

<h2> B Matrix on EEG Data: ***HVHA*** </h2>
<table>
  <tr>
    <td><img class="plain" src="assets/norm_HVHA_S1.png" height=350></td>
    <td><img class="plain" src="assets/norm_HVHA_S2.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 1: HVHA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 2: HVHA</sub></td>
  </tr>
  <tr>
    <td><img class="plain" src="assets/norm_HVHA_S3.png" height=350></td>
    <td><img class="plain" src="assets/norm_HVHA_S4.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 3: HVHA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 4: HVHA</sub></td>
  </tr>
 </table>

</section>

<section>


<img class="plain" src="assets/norm_HVHA.png" alt="Trial 5, Averaged" width="60%">

</section>

---

<!-- .slide: data-background="#ffffff" class="light" -->
<section>
<h2> B Matrix on EEG Data: ***HVLA*** </h2>
<table>
  <tr>
    <td><img class="plain" src="assets/norm_HVLA_S1.png" height=350></td>
    <td><img class="plain" src="assets/norm_HVLA_S2.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 1: HVLA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 2: HVLA</sub></td>
  </tr><section>
  <tr>
    <td><img class="plain" src="assets/norm_HVLA_S3.png" height=350></td>
    <td><img class="plain" src="assets/norm_HVLA_S4.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 3: HVLA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 4: HVLA</sub></td>
  </tr>
 </table>

</section>

<section>


<img class="plain" src="assets/norm_HVLA.png" alt="Trial 5, Averaged" width="60%">
</section>

---

<!-- .slide: data-background="#ffffff" class="light" -->

<h2> B Matrix on EEG Data: ***LVHA*** </h2>
<section>
<table>
  <tr>
    <td><img class="plain" src="assets/norm_LVHA_S1.png" height=350></td>
    <td><img class="plain" src="assets/norm_LVHA_S2.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 1: LVHA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 2: LVHA</sub></td>
  </tr>
  <tr>
    <td><img class="plain" src="assets/norm_LVHA_S3.png" height=350></td>
    <td><img class="plain" src="assets/norm_LVHA_S4.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 3: LVHA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 4: LVHA</sub></td>
  </tr>
 </table>

</section>

<section>

<img class="plain" src="assets/norm_LVHA.png" alt="Trial 5, Averaged" width="60%">

</section>

---

<!-- .slide: data-background="#ffffff" class="light" -->

<h2> B Matrix on EEG Data: ***LVLA***  </h2>
<section>


<table>
  <tr>
    <td><img class="plain" src="assets/norm_LVLA_S1.png" height=350></td>
    <td><img class="plain" src="assets/norm_LVLA_S2.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 1: LVLA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 2: LVLA</sub></td>
  </tr>
  <tr>
    <td><img class="plain" src="assets/norm_LVLA_S3.png" height=350></td>
    <td><img class="plain" src="assets/norm_LVLA_S4.png" height=350></td>
  </tr>
  <tr>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 3: LVLA</sub></td>
    <td style="text-align: center; vertical-align: middle;"><sub>Subject 4: LVLA</sub></td>
  </tr>
 </table>

</section>

<section>

<img class="plain" src="assets/norm_LVLA.png" alt="Trial 5, Averaged" width="60%">

</section>
















