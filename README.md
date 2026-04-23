# GlassesNoGlasses 

A binary image classifier that answers one simple question — is this person wearing glasses or not?

Built a custom CNN from scratch using TensorFlow/Keras, trained on a Kaggle dataset, and managed to cross the 90% validation accuracy mark. No transfer learning, no pretrained weights — just a network designed and trained from the ground up.

---

## What it does

Give it a face image, and it'll tell you whether the person is wearing glasses. That's it. Simple problem, but a great exercise in understanding how convolutional networks actually learn visual features — edges, shapes, and eventually something that resembles "glasses."

---

## How it's built

- **Framework:** TensorFlow / Keras
- **Model:** Custom CNN (built from scratch)
- **Dataset:** Sourced from Kaggle — two classes: `glasses` and `no_glasses`
- **Notebook:** Everything lives in a single Jupyter notebook — data loading, preprocessing, model definition, training, and evaluation

The model was trained on a GPU (NVIDIA RTX 2050), which made iteration significantly faster. If you're running it on CPU, expect longer training times.

---

## Results

| Metric | Value |
|---|---|
| Validation Accuracy | ~90%+ |
| Classes | Glasses / No Glasses |

---

## Getting started

### Prerequisites

```bash
pip install tensorflow numpy matplotlib jupyter
```

### Running the notebook

```bash
git clone https://github.com/ShidhantSah/GlassesNoGlasses.git
cd GlassesNoGlasses
jupyter notebook
```

Open the notebook and run the cells top to bottom. Make sure your dataset is in the expected directory — the notebook will tell you if something's missing.

### Dataset

The dataset used is available on Kaggle. Download it and place it in a `data/` folder at the root of the project before running. The notebook expects two subdirectories: `glasses/` and `no_glasses/`.

---

## Notes

- If you see warnings about `cuDNN` or `cuBLAS` registration on startup, don't worry — those are known TensorFlow packaging quirks and don't affect training or results.
- The `compile_metrics` warning after loading a saved model is also harmless — metrics populate once you call `model.evaluate()`.
- To suppress the oneDNN log, set `TF_ENABLE_ONEDNN_OPTS=0` in your environment.

---

## What I learned

This was a good exercise in building CNNs without leaning on pretrained models. The interesting part wasn't getting it to work — it was figuring out why it *wasn't* working at first (wrong input shape, data not normalized, too many filters too early). Getting past 90% on a custom architecture felt like a proper win.

---

## License

MIT — use it however you like.
