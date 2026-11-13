# MELD Multimodal Emotion Recognition

## Project Overview

This project explores **multimodal emotion recognition** using the MELD (Multimodal EmotionLines Dataset). It investigates how textual and audio information can be used to identify emotions expressed in conversational utterances.

The project implements deep learning models using **Bidirectional Gated Recurrent Units (BiGRU)** and explores multimodal learning and attention-based approaches.

The system classifies utterances into seven emotion categories:

- Anger
- Disgust
- Fear
- Joy
- Neutral
- Sadness
- Surprise

## Objectives

- Build an audio-based emotion recognition model.
- Build a text-based emotion recognition model.
- Develop a multimodal model combining audio and text information.
- Experiment with attention mechanisms and class-weighting strategies.
- Compare model performance using classification metrics and confusion matrices.

## Dataset

**MELD – Multimodal EmotionLines Dataset**

MELD contains conversational utterances from the television series *Friends*, annotated with emotion and sentiment labels.

The standard dataset contains:

| Split | Number of utterances |
|---|---:|
| Training | 9,989 |
| Validation | 1,109 |
| Testing | 2,610 |

The original dataset contains video, audio, and text information. Raw dataset files are not included in this repository.

## Methodology

### 1. Audio Processing
- Extracted audio features from utterances.
- Used Mel-Frequency Cepstral Coefficients (MFCC).
- Extracted 40 MFCC features.
- Used a maximum sequence length of 200 frames.
- Trained an Audio-BiGRU model.

### 2. Text Processing
- Processed textual utterances.
- Converted text into numerical sequences using tokenization.
- Trained a Text-BiGRU model to learn contextual information.

### 3. Multimodal Emotion Recognition
- Combined audio and textual representations.
- Developed a Multimodal-BiGRU model.
- Experimented with model tuning and class-weighting techniques.
- Explored an attention-based multimodal architecture.

### 4. Model Evaluation

Models were evaluated using:
- Accuracy
- Precision
- Recall
- Macro F1-score
- Weighted F1-score
- Confusion matrices

## Experimental Results

The following results were obtained during model experimentation.

| Model | Accuracy | Macro F1 | Weighted F1 |
|---|---:|---:|---:|
| Audio-BiGRU | 15.21% | 0.1270 | 0.1688 |
| Text-BiGRU | 28.39% | 0.2435 | 0.3061 |
| Original Multimodal-BiGRU | 27.05% | 0.2227 | — |
| Tuned Multimodal-BiGRU | 50.00% | 0.1663 | 0.3793 |
| Class-Weighted Multimodal-BiGRU | 28.47% | 0.2154 | 0.3038 |
| Attention Multimodal-BiGRU | 49.54% | 0.2363 | — |

*Note: A dash indicates that the corresponding metric was not retained in the available experiment results. Results are from separate experimental configurations and should not be interpreted as a direct controlled comparison.*

## Results and Observations

- The Text-BiGRU model performed better than the Audio-BiGRU model in the initial experiments.
- The tuned multimodal model achieved 50.00% test accuracy.
- The attention-based multimodal model achieved 49.54% test accuracy.
- Macro F1-scores indicate that recognizing minority emotion classes remains challenging.
- Class imbalance and differences in emotion representation affect model performance.

## Repository Contents

```text
MELD-Multimodal-Emotion-Recognition/
│
├── Audio_BiGRU.keras
├── Text_BiGRU.keras
├── Multimodal_BiGRU.keras
│
├── emotion_labels.json
├── tokenizer.json
│
├── Final_Results/
│   ├── audio_confusion_matrix.csv
│   ├── audio_confusion_matrix.png
│   ├── classification_reports.json
│   ├── emotion_labels.json
│   ├── model_performance_comparison.csv
│   ├── multimodal_accuracy.png
│   ├── multimodal_confusion_matrix.csv
│   ├── multimodal_confusion_matrix.png
│   ├── multimodal_loss.png
│   ├── text_confusion_matrix.csv
│   └── text_confusion_matrix.png
│
└── .gitignore
```

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Scikit-learn
- Audio feature extraction
- Natural Language Processing
- Deep Learning
- Bidirectional GRU Networks

## Limitations and Future Scope

- Improve recognition of underrepresented emotion categories.
- Investigate more effective audio-text fusion strategies.
- Experiment with pretrained audio and language models.
- Improve generalization across different conversational settings.
- Explore real-time multimodal emotion recognition.

## Disclaimer

This project is developed for academic and research purposes. Its predictions are experimental and should not be treated as definitive assessments of a person's emotional state.

## Author

**Srinidhi**
