<!-- .slide: data-background="#500000" class="dark" -->

# An Unknown B Matrix with Unknown Inputs

## T. Griffith
#### Quantum Seminar

#### July 09, 2021

---

<!-- .slide: data-background="#ffffff" class="light" -->

# 1. fMRI Comparisons
# 2. UIO Recap
# 3. Optimized Parameterizations
# 4. Identifying the "Best Fit" B Matrix for the Brain
# 5. Application to Emotion Data
# 6. Application to Movement Data
# 7. Perturbations

---

<!-- .slide: data-background="#ffffff" class="light" -->

## 1. fMRI Comparisons

---

<!-- .slide: data-background="#ffffff" class="light" -->

## Mode 1

<img class="plain" src="assets/square_quad_4_361.gif" alt="Trial 5, Averaged" width="40%">
<img class="plain" src="assets/tiled_3_flip.png" alt="Trial 5, Averaged" width="40%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

## 2. UIO Recap

---

<!-- .slide: data-background="#ffffff" class="light" -->

# UIO Review: Estimator Architecture


<img class="plain" src="assets/adapt_est.png" alt="Trial 5, Averaged" width="50%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

# A Polynomial Basis
{$1,x,x^2,x^3,\ldots,x^n$}

$u(t)=1+2t+0.5t^2$

<blockquote cite="http://www.worldwildlife.org/who/index.html">
    In some cases the natural basis functions for $u(t)$ are not clearly defined by the available data. For such cases it is usually effective to use a polynomial spline waveform-model
</blockquote>

<img class="plain" src="assets/poly_basis.png" alt="Trial 5, Averaged" width="50%">

<div style="text-align: right"> <small>Johnson, C. D. (1989, January). Effective techniques for the identification and accommodation of disturbances. In Pros. 3rd Annual NASA/DOD Controls-Structures Interaction (CSI) Technical Conf. (p. 163).</small></div>


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

## 3. Optimized Parameterizations

---

<!-- .slide: data-background="#ffffff" class="light" -->

# Convex Optimization
an optimization problem in which the objective function is a ***convex function*** and the feasible set is a ***convex set***

---

<!-- .slide: data-background="#ffffff" class="light" -->

# the objective function is a ***convex function***
<img class="plain" src="assets/convex_function_ex.png" alt="Trial 5, Averaged" width="75%">

<div style="text-align: right"> <small>
<a href="https://en.wikipedia.org/wiki/Convex_function#/media/File:ConvexFunction.svg">Image Source</a>
</small></div>

---

<!-- .slide: data-background="#ffffff" class="light" -->

# the feasible set is a ***convex set***
<img class="plain" src="assets/convex_set.png" alt="Trial 5, Averaged" width="40%">
<img class="plain" src="assets/not_convex_set.png" alt="Trial 5, Averaged" width="40%">

<div style="text-align: right"> <small>
<a href="https://en.wikipedia.org/wiki/Convex_set">Image Source</a>
</small></div>

---

<!-- .slide: data-background="#ffffff" class="light" -->

# Important Properties of Convex Problems
- every local minimum is a global minimum
- gradient descent converges in polynomial time

---

<!-- .slide: data-background="#ffffff" class="light" -->

## 4. Best Fit B Matricies

---

<!-- .slide: data-background="#ffffff" class="light" -->

# *A* Convex Function for B matrix optimization
- $\min ||y-\hat{y}-C \Delta B \hat{u}||_2$
- ***not*** the only possible minimization

---

<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix Optimization Example
- 3x3 example
 - $\dot{\hat{x}} = A_m x + B \hat{u}$
 - $A_m \neq A$ 
- ***$\min ||y-\hat{y}-C \Delta B \hat{u}||_2$***
- $B=\begin{bmatrix} 1.2 \\\ 1 \\\ 1.6 \end{bmatrix}$, 
- $B_m=\begin{bmatrix} 1 \\\ 1 \\\ 1 \end{bmatrix}$




---

<!-- .slide: data-background="#ffffff" class="light" -->

# B Matrix Optimization Example
- $\min ||y-\hat{y}-C \Delta B \hat{u}||_2$
- $\Delta B=\begin{bmatrix} 0.18 \\\ 0 \\\ 0.37 \end{bmatrix}$, 
- $B_f=\begin{bmatrix} 1.18 \\\ 1 \\\ 1.37 \end{bmatrix}$

<img class="plain" src="assets/toy_Bopt2.png" alt="Trial 5, Averaged" width="55%">


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

# Current models
<img class="plain" src="assets/UIO_opt.jpg" alt="Trial 5, Averaged" width="45%">
<img class="plain" src="assets/Bmap2.png" alt="Trial 5, Averaged" width="45%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

## 5. Application to Emotion Data

---



<!-- .slide: data-background="#ffffff" class="light" -->


## B Matrix on EEG Data: ***Satisfaction (T1)*** 
<img class="plain" src="assets/sat_map.png" alt="Trial 5, Averaged" width="60%">



---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***Surprise (T2)*** 

<img class="plain" src="assets/surp_map.png" alt="Trial 5, Averaged" width="60%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***Fear (T8)*** 

<img class="plain" src="assets/fear_map.png" alt="Trial 5, Averaged" width="60%">



---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***HVHA (T13)*** 

<img class="plain" src="assets/HVHA_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->
## Comparing the same "emotion"

<img class="plain" src="assets/val.jpg" alt="Trial 5, Averaged" width="45%">

<div style="text-align: right"> <small>Mneimne, M., Powers, A. S., Walton, K. E., Kosson, D. S., Fonda, S., & Simonetti, J. (2010). Emotional valence and arousal effects on memory and hemispheric asymmetries. Brain and Cognition, 74(1), 10-17.</small></div>


---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***HVHA*** 

<img class="plain" src="assets/HVHA_map.png" alt="Trial 5, Averaged" width="60%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***HVLA*** 

<img class="plain" src="assets/HVLA_map.png" alt="Trial 5, Averaged" width="60%">


---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***LVHA*** 

<img class="plain" src="assets/LVHA_map.png" alt="Trial 5, Averaged" width="60%">



---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***LVLA***  

<img class="plain" src="assets/LVLA_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***Avg. Quadrants***  

<img class="plain" src="assets/all_emot_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## 6. Application to Movement Data

---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***Left Hand***  

<img class="plain" src="assets/lh_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***Right Hand***  

<img class="plain" src="assets/rh_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***Resting***  

<img class="plain" src="assets/rest_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## B Matrix on EEG Data: ***All Averages***  

<img class="plain" src="assets/all_hand_map.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## 7. Perturbations (V.)

---

<!-- .slide: data-background="#ffffff" class="light" -->

## Systems with unmodeled dynamics
- $\dot{x}=A_m x + B_m u$
- $y=C_m x$
- b.c. of uncertainty in real parameters:
 - $A_m = A + \sum \delta_i A_i$
 - $B_m = B + \sum \delta_i B_i$
 - $C_m = C+ \sum \delta_i C_i$

---

<!-- .slide: data-background="#ffffff" class="light" -->

## Collect the uncertainty 
- $A_m = A + \sum \delta_i A_i = A+W_2 \Delta W_1$

<img class="plain" src="assets/perturb.png" alt="Trial 5, Averaged" width="60%">

---

<!-- .slide: data-background="#ffffff" class="light" -->

## Simple Example
- $A= \begin{bmatrix} -3 & -2 \\\ 7 & -1 \end{bmatrix}$
- Parametric uncertainty in 2 degrees:
 - $A_1=\begin{bmatrix} -w_1 & w_1 \\\ w_1 & -w_1 \end{bmatrix}$
 - $A_2=\begin{bmatrix} 0 & -w_2 \\\ 2 w_2 & 0 \end{bmatrix}$

- $A_m = A + \delta_1 \begin{bmatrix} -w_1 & w_1 \\\ w_1 & -w_1 \end{bmatrix} + \delta_2 \begin{bmatrix} 0 & -w_2 \\\ 2 w_2 & 0 \end{bmatrix}$
- $A_m = A + \begin{bmatrix} -w_1 & 0 & -w_2 \\\ w_1 & 2 w_2 & 0 \end{bmatrix} \begin{bmatrix} \delta_1 & 0 & 0 \\\ 0 & \delta_2 & 0 \\\ 0 & 0 & \delta_2 \end{bmatrix} \begin{bmatrix} 1 & -1 \\\ 1 & 0 \\\ 0 & 1 \end{bmatrix} $ 

---

<!-- .slide: data-background="#ffffff" class="light" -->

## EEG Example





















