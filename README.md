# Audio QA Dataset

This repository contains a collection of audio clips along with annotated question-answer pairs stored in a structured metadata file.

## AUDITA

This dataset accompanies the paper:

**AUDITA: A New Dataset to Audit Humans vs. AI Skill at Audio QA**  
Tasnim Kabir, Dmytro Kurdydyk, Aadi Palnitkar, Liam Dorn, Ahmed Haj Ahmed, and Jordan Lee Boyd-Graber (2026)

- **ACL Findings 2026:** https://aclanthology.org/2026.findings-acl.1292/
- **arXiv Preprint:** https://arxiv.org/abs/2604.21766

## 🔎 Dataset Explorer

You can explore the dataset interactively at:

**https://manchester.umiacs.umd.edu/audio**

The explorer allows you to:

- Browse questions by source dataset
- Browse questions by audio category
- Listen to audio clips
- View question-answer pairs and metadata

## Citation

If you use this dataset, please cite the ACL Findings paper:

```bibtex
@inproceedings{kabir-etal-2026-audita,
    title = "{AUDITA}: A New Dataset to Audit Humans vs. {AI} Skill at Audio {QA}",
    author = "Kabir, Tasnim and
      Kurdydyk, Dmytro and
      Palnitkar, Aadi and
      Dorn, Liam and
      Ahmed, Ahmed Haj and
      Boyd-Graber, Jordan Lee",
    editor = "Liakata, Maria and
      Moreira, Viviane P. and
      Zhang, Jiajun and
      Jurgens, David",
    booktitle = "Findings of the Association for Computational Linguistics: ACL 2026",
    month = jul,
    year = "2026",
    address = "San Diego, California, United States",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2026.findings-acl.1292/",
    pages = "25922--25951",
    ISBN = "979-8-89176-395-1"
}
```

If you wish to cite the preprint instead:

```bibtex
@article{kabir2026audita,
  title={AUDITA: A New Dataset to Audit Humans vs. AI Skill at Audio QA},
  author={Kabir, Tasnim and Kurdydyk, Dmytro and Palnitkar, Aadi and Dorn, Liam and Ahmed, Ahmed Haj and Boyd-Graber, Jordan Lee},
  journal={arXiv preprint arXiv:2604.21766},
  year={2026}
}
```

## 📁 Folder Structure

```text
.
├── audio/             # Contains the audio files referenced in the metadata
└── combined.json      # Metadata with QA pairs and file references
```

## 📄 File Descriptions

### `combined.json`

A list of JSON objects, each representing a question-answer annotation for an audio file.

## Dataset Overview

This dataset consists of **9,690 human-ready question-answer pairs**, organized as follows.

### OUR Sources

#### Quizbowl-style

- Pavements: **673** questions
- Audio-Packets: **1,649** questions

#### Trivia-style

- Quizmasters: **4,138** questions

**Subtotal (OUR): 6,460 questions**

### EXTERNAL Sources

#### Close-Ended Questions

- OpenAQA: **882** questions
- ClothoAQA: **323** questions

#### Open-Ended Questions

- OpenAQA: **2,025** questions

**Subtotal (EXTERNAL): 3,230 questions**

---

**Total Human-Ready Questions: 9,690**

## Metadata Fields

Each entry in `combined.json` contains the following fields:

| Field | Description |
|------|-------------|
| `question` | The question posed about the audio content |
| `dataset` | Source dataset (e.g., `clotho_aqa`) |
| `file_name` | Path to the corresponding audio file |
| `task` | Question type (`closed_ended` or `open_ended`) |
| `ground_truth` | The correct answer |
| `Categories` | High-level category (e.g., `Character/Person`) |
| `Subcategories` | More specific category label (or `N/A`) |

### Example Entry

```json
{
  "question": "Are humans heard?",
  "dataset": "clotho_aqa",
  "file_name": "/data/clotho_aqa/Backyard nature.wav",
  "task": "closed_ended",
  "ground_truth": "yes",
  "Categories": "Character/Person",
  "Subcategories": "N/A"
}
```

> **Note:** Only the final audio files (e.g., `Backyard nature.wav` or `123456.flac`) are stored in the `audio/` directory. The `file_name` field contains the original source path; simply extract the filename and locate it in the `audio/` folder.

### `audio/`

This directory contains all audio files referenced by `combined.json` in `.wav` or `.flac` format.
