# LINE Bot with Google Cloud Functions, Gemini API and Firebase

This project is a LINE Bot deployed on Google Cloud Functions, leveraging Firebase for storing chat history and Google Gemini AI for generating responses. The bot handles text interactions, saves chat history in Firebase, and uses the Gemini model for AI-generated replies.
![image](https://github.com/user-attachments/assets/e3cf5347-b4f4-4983-af2d-89e2fadb3b46)

## Project Structure

- **main.py**: Main application logic for the LINE bot, handling webhook requests, interacting with Firebase, and generating AI responses.
- **requirements.txt**: Lists required Python libraries to install for this project.

## Flow Overview

1. **LINE Message Request**: Users send a message to the bot on LINE.
2. **Google Cloud Function Trigger**: LINE forwards the message to the webhook URL provided by Google Cloud Functions, triggering the function.
3. **Webhook Processing**:
   - The Cloud Function retrieves the message data.
   - LINE Bot SDK processes the webhook request and validates it.
4. **Message Handling**:
   - If the message is text:
     - Retrieves chat history from Firebase.
     - Processes special commands like `!清空` (clears conversation history).
     - Sends message history to the Gemini AI model to generate a response.
     - Updates chat history in Firebase.
   - If the message is non-text:
     - Responds to the user indicating that only text messages are supported.
5. **Reply to User**: The response is sent back to the user via the LINE messaging API.

## Prerequisites

- **Google Cloud Project** with Cloud Functions enabled.
- **LINE Messaging API** set up with a bot, where you have generated `Channel Access Token` and `Channel Secret`.
- **Firebase Realtime Database** configured for storing chat history.
- **Gemini AI API Key** from Google for generative responses.

## Setup

1. **Clone the Repository**:
   ```bash
   git clone <your-repo-url>
   cd <your-repo>
