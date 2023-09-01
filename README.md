# DistAdam
Work done as part of the paper: https://ieeexplore.ieee.org/document/8990403
Simulations for Large batch training using Adam Optimizer.  
The notebook shows what changes are required to be done for Large batch training such that accuracy of small batch training is maintained.  
When doing data parallel distributed training, the effective batch size for k workers is k\*n where n is the minibatch size of each worker. Therefore, data parallel distributed training is similar to doing Large batch training.  
The simulations demonstrate that 2 changes have to be made to Adam Algorithm so that it works accurately in Large batch  scenario.  
1. Change beta_1 to beta_1^k for *m* and change beta_2 to beta_2^k for *v*.  
2. Change the learning rate from eta to scale\*eta. *scale* is mentioned in the notebook.
