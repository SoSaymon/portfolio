---
title: "Emotion in TV Shows"
date: 2025-10-31T10:00:00+02:00
draft: false
startDate: "Sep 2025"
endDate: "Oct 2025"
tags:
  - NLP
  - PyTorch
  - Transformers
  - Transfer Learning
image: /images/projects/emotion.jpg
description: "AI pipeline for emotion classification in TV content"
githubLink: "https://github.com/BredaUniversityADSAI/fae2-nlpr-group-group-9/tree/main/src/krzycz_trybson"
presentationLink: "/files/Emotion-in-TV-Shows.pdf"
contributors:
  - name: "Szymon Chirowski"
    role: "Modeling, Pipeline Engineer"
    link: "https://linkedin.com/in/szymon-chirowski"
  - name: "Maciej Czerniak"
    role: "Transcription, Modeling"
    link: "https://www.linkedin.com/in/maciej-czerniak-676589307/"
  - name: "Maks Burchard"
    role: "Explainable AI"
---

## Project Overview

In this project, created for the Content Intelligence Agency, our team built a complete NLP pipeline that detects and classifies emotions expressed in television content. The goal was to design a local, affordable, and transparent alternative to expensive cloud-based large language model solutions, while ensuring balanced dataset representation, interpretability, and cultural adaptability.

## Technical Implementation

### Speech-to-Text Pipeline

The system processes raw video files through several stages. It first converts speech to text using both Whisper and AssemblyAI, which were evaluated using Word Error Rate (WER) metrics. AssemblyAI was selected for its superior transcription quality and lower operational cost. The resulting transcripts were translated into English and cleaned to ensure balanced emotional representation.

### Model Architecture

For modeling, we compared several approaches including Logistic Regression, Support Vector Machines, Naive Bayes, LSTMs, and Transformer models such as BERT and RoBERTa. The Transformer architecture achieved the best performance, with the final model reaching an F1 score of 0.75.

### Explainable AI Integration

We incorporated Explainable AI tools to visualize the model's attention and better understand how it interprets emotional context in text. This step helped identify weaknesses, such as loss of context or misclassification of short sentences, and guided future improvements.

## Results & Impact

The final pipeline takes a video as input and outputs structured data with timestamps, transcribed text, and emotion labels across six core emotions: happiness, sadness, anger, surprise, fear, and disgust. The project demonstrates how modern NLP techniques can bring affordable and interpretable emotion analysis to creative and production environments.

## Technologies Used

- **NLP**: Transformers (BERT, RoBERTa), Transfer Learning
- **Speech-to-Text**: Whisper, AssemblyAI
- **Machine Learning**: PyTorch, Scikit-learn
- **Data Processing**: Pandas, NumPy
- **Explainability**: Attention visualization, Grad-CAM

## Team

This was a collaborative project with 2 other contributors from Breda University of Applied Sciences.
