# Multiscale Segmentation using HiP-CT

This is the official repository for the publication entitled **Multiscale Segmentation using Hierarchical Phase-contrast Tomography and Deep Learning**

# Folder Structure

```
	├── LICENSE
	├── main.py
	├── notebooks # Example notebooks
	├── pyproject.toml # Python environment requirement
	├── README.md
	├── registration
	│   ├── LICENSE
	│   ├── README.md
	│   ├── registration_lists # Common points for the registration
	│   └── tfms # Registration transformations
	├── segmentation
	│   ├── models # Models used 
	│   ├── postprocessing
	│   └── preprocessing
	└── uv.lock
```

# Contents
1. [Segmentation](/segmentation/S_README.md)
2. [Registration](/registration/R_README.md)

# Python environment configuration
To set up the environment, [uv](https://docs.astral.sh/uv/) is used:
```
git clone https://github.com/UCL-MSM-Bio/2025-zhou-hipct-hierarchical-segmentation.git
cd 2025-zhou-hipct-hierarchical-segmentation
uv sync

# after that, configure the nnUNet environemnt (not integrated in uv)
source .venv/bin/activate
cd segmentation/models/nnUNet
pip install -e .
```
If you prefer using conda, please install the packages in the *pyproject.toml*, but you are still required to install nnUNet using pip (see the nnUNet official installation [document](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/installation_instructions.md)).

Before using nnUNet, the paths are required to be set up: [link](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/setting_up_paths.md). A simple way is to modify the **path.py** file under *segmentation/models/nnUNet/nnunetv2*

# Data Availability
The high-resolution manually annotated data (in 2.58 um/voxel ~ 5.2 um/voxel) are available at https://doi.org/10.5281/zenodo.15397768.

The complete HiP-CT kidney volumes are available at [HOAHub Portal](https://human-organ-atlas.esrf.fr/). The DOIs are in the manuscript.

# Citation
```
@article{zhou2026multiscale,
  title={Multiscale segmentation using hierarchical phase-contrast tomography and deep learning},
  author={Zhou, Yang and Aslani, Shahab and Javanmardi, Yousef and Brunet, Joseph and Stansby, David and Carroll, Saskia and Bellier, Alexandre and Ackermann, Maximilian and Tafforeau, Paul and Lee, Peter D and others},
  journal={PLOS Computational Biology},
  volume={22},
  number={2},
  pages={e1013923},
  year={2026},
  publisher={Public Library of Science San Francisco, CA USA}
}
@article{walsh2021imaging,
  title={Imaging intact human organs with local resolution of cellular structures using hierarchical phase-contrast tomography},
  author={Tafforeau, P and Wagner, WL and Jafree, DJ and Bellier, A and Werlein, C and K{\"u}hnel, MP and Boller, E and Walker-Samuel, S and Robertus, JL and others},
  journal={Nature methods},
  volume={18},
  number={12},
  pages={1532--1541},
  year={2021},
  publisher={Nature Publishing Group US New York}
}
```
