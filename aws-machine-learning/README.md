# AWS Machine Learning & AI Services

## Overview

This section covers the main AWS managed Machine Learning and Artificial Intelligence services.

The goal is not to build or train complex machine learning models, but to understand which AWS AI service should be used for a specific use case.

---

## Amazon Rekognition

Amazon Rekognition is an image and video analysis service.

### Main use cases
- Object and scene detection
- Facial analysis
- Face comparison
- Text detection in images
- Content moderation
- Celebrity recognition
- Video analysis

### Key Point
**Rekognition = Images & Videos**

---

## Amazon Transcribe

Amazon Transcribe converts speech into text.

### Main use cases
- Automatic transcription
- Meeting transcription
- Call center recordings
- Subtitle generation
- Speech analytics

### Key Point
**Transcribe = Speech → Text**

---

## Amazon Polly

Amazon Polly converts text into natural-sounding speech.

### Main use cases
- Voice assistants
- Audiobooks
- Accessibility
- Automated announcements
- Text-to-speech applications

### Key Point
**Polly = Text → Speech**

---

## Amazon Translate

Amazon Translate provides automatic language translation.

### Main use cases
- Website translation
- Application localization
- Multilingual communication
- Large-scale document translation

### Key Point
**Translate = Language → Another Language**

---

## Amazon Lex

Amazon Lex allows developers to build conversational interfaces using voice and text.

It uses the same conversational technologies used by Amazon Alexa.

### Main use cases
- Chatbots
- Virtual assistants
- Customer service bots
- Voice interfaces

### Key Point
**Lex = Chatbots & Conversational AI**

---

## Amazon Connect

Amazon Connect is AWS's cloud-based contact center service.

It can integrate with services such as Amazon Lex for automated customer interactions.

### Main use cases
- Call centers
- Customer support
- Interactive voice response
- Automated support using Lex

### Key Point
**Connect = Cloud Contact Center**

---

## Amazon Comprehend

Amazon Comprehend uses Natural Language Processing (NLP) to analyze text.

### Main capabilities
- Sentiment analysis
- Entity recognition
- Key phrase extraction
- Language detection
- Topic modeling

### Example

A company wants to automatically determine whether customer reviews are positive or negative.

→ **Amazon Comprehend**

### Key Point
**Comprehend = Understand & Analyze Text**

---

## Amazon Comprehend Medical

Amazon Comprehend Medical is designed to extract information from unstructured medical text.

### Main use cases
- Medical records
- Clinical notes
- Diagnoses
- Medications
- Medical conditions and treatments

### Key Point
**Comprehend Medical = NLP for Medical Data**

---

## Amazon SageMaker

Amazon SageMaker is AWS's fully managed Machine Learning platform.

It allows developers and data scientists to:

- Build ML models
- Train models
- Tune models
- Deploy models
- Monitor models

Unlike services such as Rekognition or Comprehend, SageMaker is used when you need to create or train your **own machine learning models**.

### Key Point
**SageMaker = Build, Train & Deploy ML Models**

---

## Amazon Forecast

Amazon Forecast is a time-series forecasting service.

It uses machine learning to predict future values based on historical data.

### Main use cases
- Sales forecasting
- Inventory forecasting
- Demand prediction
- Resource planning
- Financial forecasting

### Example

Predicting how many products will be sold next month based on previous sales.

→ **Amazon Forecast**

### Key Point
**Forecast = Predict Future Values**

---

## Amazon Kendra

Amazon Kendra is an intelligent search service powered by machine learning.

It allows organizations to search across large collections of internal documents and data.

### Main use cases
- Enterprise search
- Internal knowledge bases
- Document search
- FAQ systems

### Key Point
**Kendra = Intelligent Enterprise Search**

---

## Amazon Personalize

Amazon Personalize is a recommendation service.

It uses machine learning to provide personalized recommendations to users.

### Main use cases
- Product recommendations
- Content recommendations
- Personalized ranking
- User-specific suggestions

### Example

An e-commerce website recommends products based on a customer's previous activity.

→ **Amazon Personalize**

### Key Point
**Personalize = Recommendation Engine**

---

## Amazon Textract

Amazon Textract automatically extracts text and structured data from scanned documents.

Unlike basic OCR, Textract can understand:

- Forms
- Tables
- Key-value pairs
- Documents

### Main use cases
- Invoice processing
- Form processing
- Document digitization
- Automated data extraction

### Key Point
**Textract = Extract Text & Data from Documents**

---

# Quick Comparison

| AWS Service | Purpose |
|---|---|
| **Rekognition** | Analyze images and videos |
| **Transcribe** | Speech → Text |
| **Polly** | Text → Speech |
| **Translate** | Language translation |
| **Lex** | Build chatbots |
| **Connect** | Cloud contact center |
| **Comprehend** | Analyze text with NLP |
| **Comprehend Medical** | Analyze medical text |
| **SageMaker** | Build, train and deploy ML models |
| **Forecast** | Time-series forecasting |
| **Kendra** | Intelligent enterprise search |
| **Personalize** | Recommendation engine |
| **Textract** | Extract text/data from documents |

---

# Exam Cheat Sheet

```text
Image / Video analysis        → Rekognition
Speech to Text                → Transcribe
Text to Speech                → Polly
Language Translation          → Translate
Chatbot                       → Lex
Call Center                   → Connect
Text / Sentiment Analysis     → Comprehend
Medical Text Analysis         → Comprehend Medical
Custom ML Model               → SageMaker
Future / Demand Prediction    → Forecast
Enterprise Document Search    → Kendra
Recommendations               → Personalize
Forms / Tables / OCR          → Textract
