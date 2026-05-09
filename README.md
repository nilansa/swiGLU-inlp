# Probing Devanagari as a Candidate Latent Bridge in Multilingual Indic Language Models
Mechanistic Interpretability study on Indic to Indic translation tasks

## Overview 
This project investigates the internal mechanics of multilingual Indic Large Language Models (LLMs). Specifically, we ask: **When an Indic model generates text in a non-Devanagari script (e.g., Bengali, Odia, or Gujarati), does it internally route through a Devanagari "bridge" representation?** 

Building on the conceptual framework of *RomanLens(Saji et.al, 2025)* (which identified latent Romanization as a bridge), this research adapts mechanistic interpretability techniques to the Indic script space. **We demonstrate that Devanagari often acts as a pronunciation-preserving latent bridge in models like Sarvam-1**

## Key Features
**Latent Bridge Probing:** Using Logit Lens to project intermediate hidden states into vocabulary space to detect transient mass on Devanagari tokens

**Multi-Task Audit:** Evaluates bridge behavior across three generation settings: Translation, Repetition, and Cloze

**Tokenizer-Aware Interpretation:** A strict filtering pipeline that audits tokenizer fragmentation and scorable coverage to distinguish between the absence of a bridge and its low observability.

**Cross-Lingual Scope:** Primary analysis covers Bengali, Gujarati, Odia, Assamese, and Dravidian languages (Tamil, Telugu, Malayalam).

## Methodology
The project follows a three-stage Latent Bridge Pipeline Architecture/

--> **Concept & Data Preparation:** Lexicon bootstrapping followed by a Tokenizer Audit to analyze how the model fragments concept terms.

--> **Analysis & Interrogation:** Running the Logit Lens on a curated, filtered dataset to isolate latent features.
Devanagari Bridge Construction: We define a bridge as a pronunciation-preserving Devanagari transliteration of the target word, distinct from a Hindi lexical translation. 

## Main Findings
Our evidence supports a cautious but positive identification of Devanagari bridges in certain linguistic branches
.
**Strong Positive Evidence:** **Bengali, Gujarati, and Odia** show significant bridge signals. Bengali and Odia specifically exhibit repeated "bridge spikes" in late-layer trajectories.

**Intermediate Evidence:** **Assamese** shows localized first-stage peaks but with a weaker signal than Odia or Gujarati.

**Low Observability (Weak Signal):** **Tamil, Telugu, and Malayalam** remain weak under the current probe. This is interpreted as a limitation of bridge observability due to heavy tokenizer fragmentation in these scripts rather than proof of bridge absence.

**Task Dynamics:** Repetition is the strongest task for bridge detection, likely because it places a lower semantic burden on the model.

## RESULTS 

**Odia Batch Results**
<img width="1250" height="395" alt="image" src="https://github.com/user-attachments/assets/64b046f6-a4ea-4303-b70c-797caad75efa" />

<img width="1237" height="402" alt="image" src="https://github.com/user-attachments/assets/20e10c8d-9078-449d-a5c3-b1c533bb915d" />

<img width="1237" height="392" alt="image" src="https://github.com/user-attachments/assets/4a1728bd-26d2-4ae7-b7b0-92ea99a1769b" />

**Bengali Batch Results**

<img width="1494" height="475" alt="image" src="https://github.com/user-attachments/assets/b9f77200-1c3c-4203-a108-adeddd7d7405" />

<img width="1501" height="467" alt="image" src="https://github.com/user-attachments/assets/b1f288e8-7710-4958-a679-dddc50de1bd5" />

<img width="1487" height="472" alt="image" src="https://github.com/user-attachments/assets/b55f099a-0985-473b-b37e-1a3e016fb532" />







