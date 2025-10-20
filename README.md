# Emotion Classification with DSPy + GEPA

Text emotion classifier built with [DSPy](https://github.com/stanfordnlp/dspy) and optimized using GEPA (Generalized Expectation-driven Prompt Augmentation).

Classifies text into: **sadness**, **joy**, **love**, **anger**, **fear**

## Setup

```bash
pip install dspy-ai pandas python-dotenv
```

Create `.env` file:
```
GEMINI_API_KEY=your_api_key_here
```

## Usage

1. **[01_data_prep.ipynb](01_data_prep.ipynb)** - Prepare train/val data from [Kaggle Emotion Dataset](https://www.kaggle.com/datasets/parulpandey/emotion-dataset/data)
2. **[02_classify.ipynb](02_classify.ipynb)** - Train with `dspy.Predict` (46% → 54% accuracy)
3. **[03_classify_cot.ipynb](03_classify_cot.ipynb)** - Train with `dspy.ChainOfThought` for reasoning

## Results

| Approach            | Baseline | Optimized |
| ------------------- | -------- | --------- |
| dspy.Predict        | 46%      | 54%       |
| dspy.ChainOfThought | ~50%     | ~56%      |

GEPA automatically improves prompts by learning nuanced emotional interpretation rules from training feedback.
