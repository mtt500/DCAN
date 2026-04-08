# DCAN Model - Code Attribution

## Project Overview

This project implements a DCAN-based code attribution model. The model identifies which generative model a code sample originates from by disentangling shared (common) features and model-specific features, thereby improving attribution accuracy.

## Key Features

- **Disentangled Feature Learning**: Decomposes code representations into common features and model-specific features  
- **Based on UniXCoder**: Uses the pretrained UniXCoder model as the encoder  
- **Multi-language Support**: Supports multiple programming languages such as Python and Java  
- **Multiple Code Modes**: Supports both plain code and code with comments  


## File Description

### Core Files

- **[run.py](run.py)** - Model training script  
- **[eval.py](eval.py)** - Model evaluation script  

## Usage

### Train the Model

```bash
python run.py --language python --mode plain
```

Arguments:
- `--language`: Programming language (e.g., python, java)
- `--mode`: Code mode (options: plain, comment)
  - `plain`: Code only
  - `comment`: Code with comments

### Evaluate the Model

```bash
python eval.py
```

You need to specify or modify the following configurations either in the script or via command-line arguments:
- Model path
- Data path
- Output directory

## Data Format

The data should be in JSONL format, with each line containing:

```json
{
  "filename": "question_id",
  "anchor_code": "code content",
  "label": 0,
  "anchor_model": "model name"
}
```

## Dependencies

- Python 3.7+
- PyTorch 1.9+
- transformers
- scikit-learn
- numpy
- matplotlib
- tqdm

## Reference
```bash
@article{guo2026codefingerprints,
  title={Code Fingerprints: Disentangled Attribution of LLM-Generated Code},
  author={Guo, Jiaxun and Yang, Ziyuan and Sun, Mengyu and Wang, Hui and Lu, Jingfeng and Zhang, Yi},
  journal={arXiv preprint arXiv:2603.04212},
  year={2026}
}
```
