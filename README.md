# Josh Talks Whisper Error Analysis

![Research](https://img.shields.io/badge/Project-ASR%20Error%20Analysis-0A66C2)
![Model](https://img.shields.io/badge/Model-Whisper-1F883D)
![Status](https://img.shields.io/badge/Status-Active%20Research-F59E0B)
![Updates](https://img.shields.io/badge/README-Live%20Updates-6F42C1)

## Overview
This project studies transcription quality on Josh Talks audio using Whisper outputs.
The goal is to understand how and why transcription errors happen, then build a stronger evaluation pipeline for continuous quality improvement.

### Workspace Snapshot
| Component | Description | Current Stage |
|---|---|---|
| Notebook analysis | Exploratory and comparative analysis workflow | ![Done](https://img.shields.io/badge/Done-0A8F08) |
| Clean dataset | Preprocessed Whisper data for evaluation | ![Done](https://img.shields.io/badge/Done-0A8F08) |
| Systematic error file | Structured error output for targeted review | ![Done](https://img.shields.io/badge/Done-0A8F08) |
| Normalized error file | Normalized error set for cleaner comparison | ![Done](https://img.shields.io/badge/Done-0A8F08) |
| Expanded research tasks | Deeper analysis and additional evaluation layers | ![In Progress](https://img.shields.io/badge/In%20Progress-F59E0B) |

## Problem
Automatic Speech Recognition (ASR) systems can introduce errors due to accents, speaking styles, background noise, named entities, and contextual vocabulary.
These issues reduce trust in transcripts and can impact downstream use cases.

This project focuses on measuring those errors systematically so we can improve transcription quality in a data-driven way.

## Workflow
```mermaid
flowchart LR
	A[Raw Josh Talks Audio] --> B[Whisper Transcription]
	B --> C[Clean and Organize Data]
	C --> D[Systematic Error Extraction]
	C --> E[Normalized Error Results]
	D --> F[Notebook-Based Analysis]
	E --> F
	F --> G[Insights and Next Research Tasks]
```

## What We Have Done
1. Collected and organized project datasets.
2. Prepared clean Whisper-related data for evaluation.
3. Generated systematic error outputs.
4. Generated normalized error outputs.
5. Built a notebook workflow for exploratory analysis.

## What We Achieved
| Outcome | Impact |
|---|---|
| Reproducible analysis setup | Results can be repeated and extended consistently |
| Baseline error datasets | Enables before-vs-after comparison over future iterations |
| Early error pattern visibility | Supports targeted improvement planning |

## Research Progress
![Progress](https://img.shields.io/badge/Overall%20Progress-60%25-0A66C2)

| Track | Status |
|---|---|
| Baseline setup | ![Completed](https://img.shields.io/badge/Completed-0A8F08) |
| Error categorization depth | ![In Progress](https://img.shields.io/badge/In%20Progress-F59E0B) |
| Expanded sample coverage | ![Planned](https://img.shields.io/badge/Planned-6B7280) |
| Evaluation refinement | ![Planned](https://img.shields.io/badge/Planned-6B7280) |

## Current Status
Research is ongoing. More tasks are in progress, including deeper error categorization, broader sample analysis, and stronger evaluation methodology.

## Continuous Updates
This README is a living document and will be updated as we complete new research tasks and improve analysis quality.

## Dataset Availability
The full audio dataset is not uploaded to this repository due to its large size.
Only analysis-ready artifacts and derived result files are included here for reproducibility and review.

## Project Files
- `Josh_talks  question 1 final.ipynb`
- `systematic_25_errors.csv`
- `normalized_25_errors_results.csv`
- `Josh_Talks_Whisper_Data/clean_whisper_data.csv`
- `Josh_Talks_Whisper_Data/audio/` (kept local, not uploaded due to large size)
