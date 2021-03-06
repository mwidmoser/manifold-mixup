# Manifold Mixup

## Insights

### Experiments
* 500 * 10 images
* average of 5 iterations

| Mixup on Block    | Accuracy`+` |   Accuracy`*` | Accuracy `§` |
| ----------------- | -------- | ---------- | ----------:|
| None              | 49.73%   | 49.64%     | 50.42%     |
| {0} = Input Mixup | 51.53%   | 49.94%     | **53.33%** |
| {1}               | 51.49%   | **51.17%** | 52.47%     |
| {2}               | 49.42%   | 48.95%     | 50.73%     |
| {0, 1}            | **52.40%** | 50.43%   | **53.30%** |
| {0, 2}            | 50.12%   | 50.16%     | 52.29%     |
| {1, 2}            | 51.09%   | 50.13%     | 52.38%     |
| {0, 1, 2}         | 51.86%   | 49.56%     | 52.79%     |

`+`: 100 epochs, LR-step-scheduler,
      train-data: no-crop + flip; test-data: no-crop + flip
   
`*`: 100 epochs, LR-step-scheduler, 
      train-data: crop(padding=4, mode=reflect) + flip; test-data: no-crop + no-flip

`§`: 100 epochs, CosineAnnealingLR(tmax=n_epochs),
      train-data: crop(padding=4, mode=reflect) + flip; test-data: no-crop + no-flip

## Todo
* Try different alpha values, maybe also time the training
* ~~Before flipping, crop the images (`transform.randomcrop` with padding=4)~~
* ~~Don't crop+flip testing data~~
* ~~Cosine-based learning rate scheduler~~
* Try training longer (300, 1000)
* Plot and monitor test error, loss etc
    * look at changes in test error when already at 100% accuracy

---

## Report
* https://www.overleaf.com/9273526114sjcmgbwhqyrk
---

## Manifold Mixup
* Paper: _Manifold Mixup: Better Representations by Interpolating Hidden States_ [[PDF]](http://proceedings.mlr.press/v97/verma19a/verma19a.pdf)
* Official implementation: [[Link]](https://github.com/vikasverma1077/manifold_mixup)
* Other implementations: [[Link]](https://paperswithcode.com/paper/manifold-mixup-better-representations-by#code)

---

## Standard Mixup

* Paper: _mixup: BEYOND EMPIRICAL RISK MINIMIZATION_ [[PDF]](https://openreview.net/pdf?id=r1Ddp1-Rb)
* Official implementation: [[Link]](https://github.com/facebookresearch/mixup-cifar10)
