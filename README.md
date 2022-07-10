# Anime facial images with StyleGAN
Conditional generator, transfer learning, low budget

[Read Bachelor's thesis](https://github.com/M1v1savva/anime-thesis/blob/main/thesis_final.pdf)

Google colab notebooks:<br/>
[thesis_results](https://colab.research.google.com/drive/1Yc1q1RVkKNN2b9R0usOJSsSJRTdOBN53?usp=sharing)

---

For my bachelor's thesis I generated anime and manga faces with Conditional StyleGAN and transfer learning. I trained 3 models:
- Baseline conditional model, 7000 kimgs (~10 hours), 37 labels, conditioned on hair+eyes pairs
- Transferred manga model, 7500 kimgs (~5 hours excluding baseline), label 0
- Holo model, 7500 kimgs (~5 hours excluding baseline), label 15

As a datasets I used [facial dataset from kaggle](https://www.kaggle.com/datasets/subinium/highresolution-anime-face-dataset-512x512) and custom Attack on Titan dataset for manga images. 
Note that the baseline model is conditioned on mutually exclusive tags, each tag should be put as a one-hot encoding and concatenated with random noise before feeding to the mapping network. 
Since those labels encode a pair of features (as a list) conditionality suffers a bit. For more details see the paper.

--- 

Trained network snapshots can be downloaded with gdown:
```console
gdown https://drive.google.com/uc?id=1jVQZN9OiX8jl59zWz8CHFnQP9HtfYrDv
gdown https://drive.google.com/uc?id=1ptG88Thr9Oae0cTBlPO3jRhFz-cIbmjb
gdown https://drive.google.com/uc?id=1jRbrCuOtTboDWMBSWCB82gj8Socxdr8h
```

- `cond.pkl` - conditional model with 37 labels from 0 to 36
- `manga.pkl` - manga model, use label 0 (conditionality is preserved since conditional model was used as a baseline for transfer learning)
- `holo.pkl` - holo model, use label 15

For more details see the notebooks
