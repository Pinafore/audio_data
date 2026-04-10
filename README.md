Audio QA Dataset
This repository contains a collection of audio clips along with annotated question-answer pairs stored in a structured metadata file.

📁 Folder Structure
.
├── audio/             # Contains actual audio files referenced in the metadata
└── combined.json      # Metadata with QA pairs and file references
📄 File Descriptions
combined.json
A list of JSON objects, each representing a QA annotation for an audio file.

## Human-Ready Unsplit Files Overview

This dataset consists of unsplit, human-ready question-answer files, categorized as follows:

### OUR Sources

**Quizbowl-style**
- **Pavements**: 673 questions  
- **Audio-Packets**: 1,649 questions  

**Trivia-style**
- **Quizmasters**: 4,138 questions  

**Subtotal (OUR):** **6,460** questions

### EXTERNAL Sources

**Close-Ended Questions**
- **OpenAQA**: 882 questions  
- **ClothoAQA**: 323 questions  

**Open-Ended Questions**
- **OpenAQA**: 2,025 questions  

**Subtotal (EXTERNAL):** **3,230** questions

---

**Total Human-Ready Questions:** **9,690**



Each entry contains:

Field	Description
question	The question posed about the audio content
dataset	The source dataset (e.g., clotho_aqa)
file_name	Path to the corresponding audio file
task	Type of task (e.g., closed_ended, open_ended)
ground_truth	The correct answer to the question
Categories	High-level category of the sound (e.g., Character/Person)
Subcategories	More specific label (or N/A if not applicable)

Example Entry
{
  "question": "Are humans heard?",
  "dataset": "clotho_aqa",
  "file_name": "/data/clotho_aqa/Backyard nature.wav",
  "task": "closed_ended",
  "ground_truth": "yes",
  "Categories": "Character/Person",
  "Subcategories": "N/A"
}
🔍 Note: Only the actual audio files (e.g., Backyard nature.wav or 123456.flac) are placed in the audio/ folder. You do not need to search the full path listed in file_name. Just extract the final filename from the path and look for it in the audio/ directory.

audio/ folder
This folder contains only the final audio files referenced in combined.json, in .wav or .flac format.
