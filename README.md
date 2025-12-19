# Chamorro Language AI Initiative  
Umbrella Project Blueprint

The Chamorro Language AI Initiative is a community-driven, multi-phase effort to build a sustainable digital ecosystem for the Chamorro language. This repository contains the foundational blueprint for creating open datasets, training language and translation models, developing a public Chamorro Translation API, and launching the Guam Translate website and mobile application.

---

## 1. Project Overview

### 1.1 Mission Statement
Build a community-owned Chamorro language infrastructure: open datasets, translation models, APIs, and public tools that support education, culture, government, and tourism.

### 1.2 High-Level Phases
1. Data scraping and corpus creation  
2. LLM training (translation and language models)  
3. Public Chamorro translation API  
4. Guam Translate website and mobile app  

---

## 2. Funding and Partnership Strategy

### 2.1 Target Funders
- Local government  
  - Department of Chamorro Affairs  
  - Guam Legislature (culture and education committees)  
  - Guam Department of Education  

- Tourism industry  
  - Guam Visitors Bureau  
  - Hotels, airlines, tour operators  
  - Cultural tourism initiatives  

- Nonprofits and cultural organizations  
  - Kumisión i Fino’ CHamoru  
  - Humanities Guåhan  
  - Pacific language and cultural organizations  

- Academic partners  
  - University of Guam  
  - Regional universities and linguistics departments  

- Tech philanthropy and grants  
  - Language preservation grants  
  - Open-source and digital humanities foundations  
  - Corporate CSR programs  

### 2.2 Call to Action
Join us in building the first open, community-owned Chamorro Language AI — a digital foundation for education, culture, government, and tourism in Guam. Your support will help create public datasets, translation tools, and applications that make Chamorro more accessible to future generations.

### 2.3 Contributor Invitation

**Who We Welcome**
- Developers and data engineers  
- Machine learning researchers  
- Chamorro teachers, linguists, and language workers  
- Students and community volunteers  
- Designers and UX researchers  
- Translators and cultural practitioners  

**Ways to Contribute**
- Build and maintain scraping and data pipelines  
- Clean, annotate, and validate data  
- Provide or review Chamorro texts and translations  
- Design UX for website and mobile app  
- Write documentation and guides  
- Support outreach and community governance  

---

## 3. Project 1 — Data Scraping and Corpus Creation

### 3.1 Goal
Create a legally compliant, well-structured, community-reviewed Chamorro language corpus for model training and research.

### 3.2 Key Tasks

#### 3.2.1 Source Inventory
Identify and classify candidate sources:
- Public domain dictionaries  
- Chamorro Bible  
- Guam and CNMI government documents  
- Chamorro Wikipedia  
- Cultural stories and texts (with permission)  
- Academic papers and theses  
- Community-submitted text  

Record for each source:
- License or legal status  
- Content type  
- Format (HTML, PDF, DOC, text, etc.)  

#### 3.2.2 Legal and Cultural Review
- Confirm public domain or explicit licenses  
- Request permission where required  
- Maintain a do-not-scrape list for sensitive material  
- Document cultural considerations and restrictions  

#### 3.2.3 Scraping and Ingestion
- Build modular scraping scripts  
- Normalize text (encoding, diacritics, glottal stops)  
- Store raw data with metadata (source, date, license, category)  

#### 3.2.4 Cleaning and Structuring
- Remove noise and duplicates  
- Segment into sentences, paragraphs, and parallel pairs  
- Tag metadata (language, domain, register, quality level)  

#### 3.2.5 Dataset Packaging
- Convert to Hugging Face `datasets` format  
- Define schemas and metadata  
- Create train, validation, and test splits  
- Document provenance, licenses, and limitations  

### 3.3 Deliverables
- Source inventory and licensing report  
- Scraper scripts and ingestion pipeline  
- Cleaned and structured corpora  
- Published or ready-to-publish datasets  
- Data documentation  

---

## 4. Project 2 — LLM and Translation Model Training

### 4.1 Goal
Train reliable Chamorro language and translation models using the corpus from Project 1.

### 4.2 Initial Model Scope
1. Chamorro to English translation  
2. English to Chamorro translation  
3. Chamorro-only language model  

### 4.3 Technical Stack
- Hugging Face Transformers and Datasets  
- PyTorch  
- SentencePiece or similar tokenizer  
- Cloud or on-prem GPU training  
- Model hosting via Hugging Face Hub  

### 4.4 Training Pipeline

#### 4.4.1 Data Preparation
- Build parallel datasets  
- Build monolingual Chamorro dataset  
- Reserve high-quality validation and test sets  

#### 4.4.2 Tokenizer Design
- Preserve Chamorro diacritics and glottal stops  
- Handle reduplication and affixes  
- Validate with native speakers when possible  

#### 4.4.3 Base Model Selection
- MarianMT or similar for translation  
- GPT-style model for language modeling  

#### 4.4.4 Training
- Fine-tune translation models  
- Fine-tune Chamorro language model  
- Track BLEU, chrF, perplexity, and human evaluation  

#### 4.4.5 Evaluation
- Human evaluation by Chamorro speakers  
- Error analysis and iterative refinement  

#### 4.4.6 Publishing
- Upload models to a public model hub  
- Provide model cards with training details, intended use, and limitations  

### 4.5 Deliverables
- Trained model checkpoints  
- Reproducible training scripts  
- Evaluation reports  
- Model cards and documentation  

---

## 5. Project 3 — Chamorro Translation API

### 5.1 Goal
Provide a robust, documented API for Chamorro translation and language services.

### 5.2 Core API Design

Example endpoints:
- POST /translate/chamorro-to-english  
- POST /translate/english-to-chamorro  
- POST /language-model/chamorro/generate  

Example request:
```json
{
  "text": "Håfa adai",
  "domain": "general",
  "formality": "default"
}
