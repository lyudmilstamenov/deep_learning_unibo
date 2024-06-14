# Sentence Reconstruction with Transformer Model

## Purpose
The purpose of this project is to reconstruct the original English sentence from a sequence of words that are a random permutation of that sentence. This problem is approached using a Transformer model, which predicts each token in the correct order based on the shuffled input. This project is a course project for the Deep Learning course at Alma Mater Studiorum - Università di Bologna.

## Methodology

### Data Preparation:
- **Dataset Structure:** The dataset consists of pairs of a shuffled sentence and its ordered counterpart.
- **Data Triplets:** Each data instance is split into triplets:
  - Context: Shuffled sentence.
  - Decoder Input: Beginning of the ordered sentence with a start token.
  - Label: Fully ordered sentence.

### Model Architecture:
- **Transformer Model:** Implemented to predict the probabilities for each token in the ordered sentence.
  - **Input:** Shuffled sentence and part of the ordered sentence.
  - **Output:** Predicted token for the next position in the sequence.
  - **Objective:** Predict the most probable token based on the context provided.

### Prediction Procedure:
- **Initial Setup:** Start with the shuffled sentence and a start token as the initial decoder input.
- **Prediction Loop:**
  - The model predicts the next most probable token based on the current decoder input.
  - Ensure the predicted token is selected from the remaining unused tokens in the shuffled sentence.
  - Concatenate this token to the decoder input for the next prediction iteration.
  - Repeat until all tokens of the ordered sentence are predicted.

## Course Project Details
- **Course:** Deep Learning
- **Institution:** Alma Mater Studiorum - Università di Bologna
- **Purpose:** This project serves as a course project for exploring practical applications of deep learning in natural language processing.
