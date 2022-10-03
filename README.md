# TD-GCN-Gesture
# Prerequisites
you can install all dependencies by running ```pip install -r requirements.txt```  <br />
Then you need to install torchlight by running ```pip install -e torchlight```  <br />

# Data Preparation
## Download four datasets:
1. **SHREC’17 Track** dataset from <br />
2. **DHG-14/28** dataset from <br />
3. **NTU RGB+D 60** Skeleton dataset from <br />
4. **NW-UCLA** dataset from <br />

## SHREC’17 Track dataset:
1. First, extract all files to ```/data/shrec/shrec17_dataset``` <br />
2. Then, run ```python gen_traindataset.py``` and ```python gen_testdataset.py``` <br />

## DHG-14/28 dataset:
1. First, extract all files to ```./data/DHG14-28/DHG14-28_dataset``` <br />
2. Then, run ```python python gen_dhgdataset.py```

## NTU RGB+D 60 dataset
1. First, extract all skeleton files to ```./data/ntu/nturgbd_raw``` <br />
2. Then, run ```python get_raw_skes_data.py```, ```python get_raw_denoised_data.py``` and ```python seq_transformation.py``` in sequence <br />

## NW-UCLA dataset
1. Move folder ```all_sqe``` to ```./data/NW-UCLA```

# Training
You can change the configuration in the yaml file and in the main function. We also provide four default yaml configuration files. <br />
## SHREC’17 Track dataset:
run ```python main.py --device 0 1 --config ./config/shrec17/shrec17.yaml``` <br />
## DHG-14/28 dataset:
run ```python main.py --device 0 1 --config ./config/dhg14-28/DHG14-28.yaml``` <br />
## NTU RGB+D 60 dataset:
On the benchmark of cross-view, run ```python main.py --device 0 1 --config ./config/nturgbd-cross-view/default.yaml``` <br />
On the benchmark of cross-subject, run ```python main.py --device 0 1 --config ./config/nturgbd-cross-subject/default.yaml``` <br />
## NW-UCLA dataset:
run ```python main.py --device 0 1 --config ./config/ucla/nw-ucla.yaml``` <br />

# Testing
We provide several trained weight files and place them in the checkpoints folder.
