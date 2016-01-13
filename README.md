# Verbs in COCO (V-COCO) Dataset

This repository hosts the Verbs in COCO (V-COCO) dataset and associated code to evaluate models for the Visual Semantic Role Labeling (VSRL) task as ddescribed in <a href=http://arxiv.org/abs/1505.04474>this technical report</a>. 

### Citing
If you find this dataset or code base useful in your research, please consider citing the following papers:

    @article{gupta2015visual,
      title={Visual Semantic Role Labeling},
      author={Gupta, Saurabh and Malik, Jitendra},
      journal={arXiv preprint arXiv:1505.04474},
      year={2015}
    }
    
    @incollection{lin2014microsoft,
      title={Microsoft COCO: Common objects in context},
      author={Lin, Tsung-Yi and Maire, Michael and Belongie, Serge and Hays, James and Perona, Pietro and Ramanan, Deva and Doll{\'a}r, Piotr and Zitnick, C Lawrence},
      booktitle={Computer Vision--ECCV 2014},
      pages={740--755},
      year={2014},
      publisher={Springer}
    }
    
### Installation
1. Clone repository (recursively, so as to include COCO API).
    ```Shell
    git clone --recursive https://github.com/s-gupta/v-coco.git
    ```

2. This dataset builds off <a href=http://mscoco.org/>MS COCO</a>, please download MS-COCO images and annotations. 

3. Current V-COCO release only uses a subset of MS-COCO images (Image IDs listed in ```data/splits/vcoco_all.ids```). Use the following script to pick out annotations from the COCO annotations to allow faster loading in V-COCO.  
    ```Shell
    # Assume you cloned the repository to `VCOCO_DIR'
    cd $VCOCO_DIR
    # If you downloaded coco annotations to coco-data/annotations
    python script_pick_annotations.py coco-data/annotations
    ```
    
4. Build ```coco/PythonAPI/pycocotools/_mask.so```, ```cython_bbox.so```. 
    ```Shell
    # Assume you cloned the repository to `VCOCO_DIR'
    cd $VCOCO_DIR/coco/PythonAPI/ && make
    cd $VCOCO_DIR && make
    ```

### Using the dataset
An IPython notebook, illustrating how to use the annotations in the dataset is available in ```V-COCO.ipynb```
