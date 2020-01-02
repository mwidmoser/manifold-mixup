# Manifold Mixup

## Insights

### Experiments
* 500 * 10 images
* 100 epochs
* average of 5 iterations

| Mixup on Block    | Accuracy |
| ----------------- |:--------:|
| None              | 49.73%   |
| {0} = Input Mixup | 51.53%   |
| {1}               | 51.49%   |
| {2}               | 49.42%   |
| {0, 1}            | **52.40%**   |
| {0, 2}            | 50.12%   |
| {1, 2}            | 51.09%   |
| {1, 2, 3}         | 51.86%   |

### Questions
* They claim that manifold mixup works best in the first few (or all) layers (not in the last ones). Consider Table 6 in the paper.
* We've now mixup before a block (we have three blocks), do we want it between a block, thus before an individual layer? 
* Apply mixup not only before a single block, but before multiple blocks? Use the same lambda.
* What's next?

---

## Manifold Mixup
* Paper: _Manifold Mixup: Better Representations by Interpolating Hidden States_ [[PDF]](http://proceedings.mlr.press/v97/verma19a/verma19a.pdf)
* Official implementation: [[Link]](https://github.com/vikasverma1077/manifold_mixup)
* Other implementations: [[Link]](https://paperswithcode.com/paper/manifold-mixup-better-representations-by#code)

---

## Standard Mixup

* Paper: _mixup: BEYOND EMPIRICAL RISK MINIMIZATION_ [[PDF]](https://openreview.net/pdf?id=r1Ddp1-Rb)
* Official implementation: [[Link]](https://github.com/facebookresearch/mixup-cifar10)