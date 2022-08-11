# A human-machine collaborative approach measures economic development using satellite imagery

This repository is official implementation of 'A human-machine collaborative approach measures economic development using satellite imagery'.

---  

## Software  

### Module dependencies

The code has been tested on the following environment :
```
torch==1.11.0
torchvision==0.8.2
numpy==1.19.2
scipy==1.6.2
sklearn==0.23.2
scikit-image==0.19.2
pandas==1.1.4
Pillow=8.2.0
faiss==1.5.3
```

Following command can replicate the full environment :

```pip install -r requirements.txt```

---  

## Hardware  

### GPU specification  

The code has been tested on four NVIDIA TITAN Xp GPUs  

---  

## Model description  
<img src="./Materials/Main/Fig/Figure1.png" width="600">  
To train the scoring model *siScore*, you need to follow three stages: `Stage1`, `Stage2`, `Stage3`.  
`Stage1` first conducts pre-training, and then generates the clusters from given satellite imagery via *DeepCluster*.  
`Stage2` suggests ensemble method for aggregating human-guided weak-supervision in reasonable way. *Humman* annotators first label the partial orders between the clusters from `Stage1`. Then, the *Machine* ensembles the all labels from the human, and prune some clusters for better training.  
`Stage3` trains the rank-wise score model *siScore* from the `Stage2`'s label (*Ensemble POG*).   
Please refer to `README.md` in each stage's directory (i.e., `Stage1`, `Stage2`, `Stage3`) to get started.  
Dataset in ```data``` directory is sampled example from the original dataset. The code is implemented according to its format, so use them just for the reference.  

---  

## Reproducing Figs/Tables  

---  
 
Contributor : TA, EL