<!-- .slide: data-background="#500000" class="dark" -->

# Bi-Weekly Notes

## More on OMA and DEAP



2020-04-15

---

<!-- .slide: data-background="#767171" class="dark" -->

## Last Time:

- Looked at different output only state space algorithms
- How to get a single model for cognitive state?
    - Average the eigenvectors reconstruct A
    - Average A and determine the eigenvectors

<img src="img/T5avg.png" alt="Trial 5, Averaged" style="width:500px;"> 



---

<!-- .slide: data-background="#767171" class="dark" -->

## Average the Eigenvectors:
- Reconstruct the A matrix from averaged eigenvectors
- L.I. eigenvectors, but no guarantee of orthogonality or SA

<img src="img/T36comps.png" alt="Trial 36, stats" style="width:1500px;">



---

<!-- .slide: data-background="#767171" class="dark" -->

## Average the A:
- Recalculate eigenvectors after averaging the A matrix
- L.I. eigenvectors, but again no guarantee of orthogonality or SA

<img src="img/T36avgofA.png" alt="Trial 36, A average" style="width:800px;">



---

<!-- .slide: data-background="#767171" class="dark" -->

## What if we force SA?:
- Recalculate eigenvectors after averaging the A matrix and forcing SA
- L.I., orthogonal eigenvectors for distinct eigenvalues
- Tricky C matrix

<img src="img/T36hermofA.png" alt="Trial 36, A average" style="width:700px;">
<img src="img/T16hermofA.png" alt="Trial 36, A average" style="width:700px;">



---

<!-- .slide: data-background="#767171" class="dark" -->

## What have we learned:
- OMA-data seems to be the most consistent across the data set
- If we postulate that pure emotions should be standing waves, SA transform is promising
    - Need to track the norm of the lost components somehow
    - But, need to understand why eigenvectors don't stay complex
        - SA does not restrict this
- It's too difficult for a human to look at these and learn anything



---

<!-- .slide: data-background="#767171" class="dark" -->

## Heatmaps for ML:
- A given complex mode:
    - $\phi_1=[1, -0.8, 0.4-0.3i, -1, 0.7+0.1i]$
- Represent complex mode as a heatmap:

<p align="center">
  <img src="img/test_hmap.png" alt="Trial 36, A average" style="width:600px;">
</p>

---

<!-- .slide: data-background="#767171" class="dark" -->

## Look at All Eigenvectors:

- Both for hermitian and non-hermitian case
- Hermitian is non-complex, but more modes
- non-Hermitian is complex, but fewer modes


<p align="center">
  <img src="img/T37avgofA_heat.png" alt="Trial 36, A average" style="width:700px;">
  <img src="img/T37hermofA_heat.png" alt="Trial 36, A average" style="width:700px;">
</p>

---

<!-- .slide: data-background="#767171" class="dark" -->


## Heatmaps for ML:
- Ask computer to distinguish images:

<p align="center">
  <img src="img/ml_heat1.png" alt="Trial 36, A average" style="width:700px;">
  <img src="img/ml_heat2.png" alt="Trial 36, A average" style="width:700px;">
</p>

---

<!-- .slide: data-background="#767171" class="dark" -->


## Consider all channels:
- Early work with [Bruel & Kjaer](https://www.bksv.com/en/products/Analysis-software/structural-dynamics-software/modal-measurements-and-analysis/operational-modal-analysis-8760-8761-8762)
- Treat all channels as a flat plate, look for modes

<p align="center">
  <img src="img/bruel.png" alt="Trial 36, A average" style="width:1000px;">
</p>

---

<!-- .slide: data-background="#767171" class="dark" -->

## What have we learned 2.0:
- Loosing too much information in the self-adjoint transform
    - Need least squares
    - Need to be able to transform C matrix also
- ML heatmap analysis may suggest the best algorithm/representation
  - First pass is an improvement over time series, but still not useful
- Early work with all channels is promising. 

- All plots [here](https://drive.google.com/drive/folders/1vuMJPsxFmVqm2SRdVpqBoa8_NeZ_Jn9Y?usp=sharing)

















