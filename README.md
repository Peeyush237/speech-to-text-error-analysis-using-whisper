# Josh Talks Speech and Audio Assignment Repository

This repository contains end-to-end work for a Hindi ASR research assignment based on Josh Talks conversational audio.
The workflow covers all four assignment questions:

1. Fine-tuning and evaluating Whisper-small for Hindi ASR.
2. Designing post-processing for numbers and mixed-language handling.
3. Building a large-scale Hindi word spelling quality pipeline.
4. Implementing lattice-based multi-hypothesis evaluation logic.

The repository includes notebooks, generated CSV deliverables, source spreadsheets, and supporting assignment documentation.

## Key Results (From Files in This Folder)

- Baseline Whisper-small WER (Question 1 notebook output): 86.99%
- Fine-tuned Whisper-small WER (Question 1 notebook output): 46.74%
- Relative improvement after fine-tuning: about 46.27%
- Systematic error sample size: 25 rows
- Normalization comparison sample size: 25 rows
- Mean WER before normalization (25-row sample): 0.4545
- Mean WER after normalization (25-row sample): 0.3836
- Relative WER reduction after normalization: 15.60%
- Rows improved after normalization: 23/25

## Repository Contents

### Notebooks

- Josh_talks  question 1 final.ipynb
	End-to-end Question 1 pipeline:
	data preparation, Whisper fine-tuning, FLEURS evaluation, systematic error sampling, normalization-based targeted fix analysis.

- josh_talks_question_2.ipynb
	Question 2 work:
	Hindi number normalization, text cleanup strategy, mixed-script handling, and supporting experiments around post-processing for ASR outputs.

- josh_talks_quesiton_3_v2 (1).ipynb
	Question 3 pipeline:
	multi-phase lexical filtering and spelling classification over a large unique-word list with dictionary checks, structural checks, and tokenizer heuristics.

- josh_talks_queston_4.ipynb
	Question 4 implementation:
	advanced lattice construction and lattice-aware WER using voting thresholds, insertion/deletion/substitution handling, and dynamic programming.

### CSV Deliverables

- systematic_25_errors.csv
	Rows: 25
	Columns: Prediction, Reference, WER
	Generated as systematic sampling of non-zero WER errors.

- normalized_25_errors_results.csv
	Rows: 25
	Columns: New_WER, Norm_Prediction, Norm_Reference, Prediction, Reference, WER
	Contains before/after normalization comparison for the sampled errors.

- Question_3_Final_Deliverable.csv
	Rows: 177,509
	Columns: Status (correct spelling / incorrect spelling), word
	Large-scale classified output for Question 3.

- Question_3_Final_Word_List_Expanded.csv
	Rows: 177,509
	Columns: Status (correct spelling / incorrect spelling), word
	Expanded final word-status artifact for Question 3.

### Data Folder

- Josh_Talks_Whisper_Data/clean_whisper_data.csv
	Rows: 2,522
	Columns: audio, sentence
	Training map of audio path and Hindi transcript text.
	Note: audio paths are Colab-style absolute paths and may need rewriting for local execution.

- Josh_Talks_Whisper_Data/clean_whisper_data.xlsx
	Spreadsheet version of clean whisper data.

- Josh_Talks_Whisper_Data/audio/
	Local audio chunk directory used by notebook workflows.

### Assignment Support Files

- JoshTalks_Assignment_Walkthrough.docx
	Full assignment walkthrough with methodology and links.

- Josh Talks question1 answers.docx
	Written response and taxonomy/fix explanation for Question 1.

- New_Task Assignment _ AI Researcher Intern- Speech & Audio _ Josh Talks .pdf
	Original assignment prompt document.

- FT Data.xlsx
	Fine-tuning input spreadsheet (sheet: data).

- Copy of FT Result.xlsx
	Supporting result spreadsheet (sheet: Sheet1).

- Question 4.xlsx
	Input spreadsheet for lattice evaluation experiments (sheet: Task).

## Question-Wise Summary

### Question 1: Whisper Fine-Tuning and Error Analysis

Main outputs in this repository:

- Fine-tuning/evaluation notebook: Josh_talks  question 1 final.ipynb
- Sampled error file: systematic_25_errors.csv
- Normalization comparison file: normalized_25_errors_results.csv

Highlights:

- Builds a robust preprocessing pipeline for Hindi conversational audio.
- Fine-tunes openai/whisper-small on curated Josh Talks style data.
- Evaluates on Hindi split of FLEURS.
- Performs systematic error extraction and targeted normalization analysis.

### Question 2: Post-Processing and Normalization

Main notebook:

- josh_talks_question_2.ipynb

Highlights:

- Number-word and compound number normalization ideas for Hindi text.
- Mixed-language and transliteration handling concepts.
- Utility functions for ASR output cleaning and assignment demonstrations.

### Question 3: Spelling Quality Pipeline at Scale

Main notebook and outputs:

- Notebook: josh_talks_quesiton_3_v2 (1).ipynb
- Output CSVs: Question_3_Final_Deliverable.csv, Question_3_Final_Word_List_Expanded.csv

Highlights:

- Uses lexical resources and heuristics for Hindi word quality labeling.
- Produces a large classified word list (177,509 rows).

### Question 4: Lattice WER and Multi-Model Agreement

Main notebook and input sheet:

- Notebook: josh_talks_queston_4.ipynb
- Input data: Question 4.xlsx

Highlights:

- Word-level lattice binning with model-agreement voting.
- Explicit handling of substitutions, deletions, and insertions.
- Dynamic-programming-based lattice WER computation.

## Environment and Dependencies

The notebooks were developed for Google Colab and rely primarily on:

- Python 3.x
- transformers
- datasets
- evaluate
- torch
- librosa
- pydub
- jiwer
- indic-nlp-library
- indic-transliteration
- pyiwn
- nltk
- wordfreq

Because notebook code uses Google Drive mounts and Colab-style absolute paths, local runs require path updates.

## How To Reproduce (Practical Order)

1. Start with Josh_talks  question 1 final.ipynb to understand data flow and baseline/fine-tuned evaluation.
2. Inspect systematic_25_errors.csv and normalized_25_errors_results.csv for targeted before/after error behavior.
3. Review josh_talks_question_2.ipynb for normalization and mixed-language processing logic.
4. Run josh_talks_quesiton_3_v2 (1).ipynb for large-scale lexical classification if required.
5. Run josh_talks_queston_4.ipynb with Question 4.xlsx to reproduce lattice evaluation behavior.

## Notes and Caveats

- Several notebook filenames contain spelling variants (quesiton, queston). They are retained as-is.
- Two Question 3 CSV outputs have identical schema and row count, but they are not byte-identical files.
- Some notebook cells include Colab-only setup (Google Drive mount and /content paths).

## Status

Repository status is complete for assignment submission artifacts:

- Source notebooks are present for all four questions.
- Deliverable CSVs are present.
- Supporting assignment documentation is present.

This README is now aligned with the current files in this workspace.
