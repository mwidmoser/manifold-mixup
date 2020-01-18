# Further Experiments on Parameters

_All results are avg of 5 runs; n_epochs=100_


- **Varying:** LR

    **Fixed:** CosineAnnealingLR(t_max=n_epochs), momentum=0.9, weight-decay=1e-3, no mixup
    
  | LR   | accuracy |
  |-------|-----------|
  |  0.1  | 49.42% |
  | 0.05 | 50.14% |
  | 0.02 | 51.22% |
  | 0.01 | 51.39% |
  |0.008| 50.50% |


- **Varying:** weight-decay

    **Fixed:** LR=0.01, CosineAnnealingLR(t_max=n_epochs),  momentum=0.9, no mixup

  | weight-decay | accuracy |
  |-----------------|------------|
  | 1e-3 | 50.95% |
  | 1e-4 | 50.95% |

-------------------------------------------------------
#### New: Switched to CosineAnnealingWithWarmRestarts

- **Varying:** t_max

    **Fixed:** LR=0.01, momentum=0.9, weight-decay=1e-3, no mixup
  
  |   t_max | accuracy | 
  |-----------|------------|
  | n_epochs | 50.96% |
  | n_epochs / 2 | 51.31% |
  | n_epochs / 3 | 44.60% |
  | n_epochs / 4 | 51.72% |
  | n_epochs / 10 | 52.16% |


- **Varying:** mixup, t_max

    **Fixed:** LR=0.01, momentum=0.9, weight-decay=1e-3
  
  | mixup | accuracy (n_epochs) | accuracy (n_epochs/2) | accuracy (n_epochs/10) |
  |--------|----------|-----------|---------|
  | [False,False,False] | 50.96% | 51.31% | 52.16% |
  | [True,False,False]  | 53.18% | 52.98% | 53.13% |
  | [True,True,False]  | 53.16% | 52.97%  | 52.97% |
  | [True,True,True]   | 52.83% | 52.61% | 52.42% |


- **Varying:** mixup, t_max_

    **Fixed:** LR=0.01, momentum=0.9, **weight-decay=1e-4**
  
  | mixup | accuracy (n_epochs) | accuracy (n_epochs/2) | accuracy (n_epochs/10) |
  |------|-------|-----------|--------|
  | [False,False,False] | 50.62% | 51.14% | 50.52% |
  | [True,False,False]  | 52.58% | 53.31% | 52.96% |
  | [True,True,False]  | 53.15% | 53.26% | 52.13% |
  | [True,True,True]   | 52.40% | 52.14% | 53.10% |

-------------------------------------------------------
#### New: switched to momentum=0.95

- **Varying:** mixup, t_max

    **Fixed:** LR=0.01, **momentum=0.95**, weight-decay=1e-4
    
  | mixup | accuracy (n_epochs) | accuracy (n_epochs/2) | accuracy (n_epochs/10) |
  |-------|--------------------|----------|-----------|
  | [False,False,False] | 50.47% | 50.36% | 50.53% |
  | [True,False,False]  | 53.62% | 53.47% | 53.94% |
  | [True,True,False]  | 52.85% | 52.95% | 52.02% |
