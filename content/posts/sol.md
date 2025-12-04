---
title: "Tamil Voice To English Prompt - Vibe Coding"
date: "2025-08-10"
draft: false
---

A small learning experiment with Replit - சொல் is a mobile responsive web app that converts Tamil speech into structured prompts for ChatGPT and Claude. Users can record their ideas in Tamil and get structured prompts. If you are a student trying to vibe code and want to generate quality prompts by just speaking out your requirements in Tamil, you will hopefully like சொல். 

![screenshot](/images/1753418403664.jpg)

## Core Features

### Voice Recording
- **Tamil Speech Capture:** Record audio directly in the browser using the Web Speech API.
- **Real-time Audio Visualization:** Provides waveform-based visual feedback while recording.
- **Whisper AI Transcription:** Uses OpenAI Whisper for high-accuracy Tamil speech-to-text conversion.
- **Mobile Responsive:** Optimized for both desktop and mobile devices.

### AI-Powered Processing
- **Smart Prompt Structuring:** Transforms Tamil narration into clean, well-formatted English prompts.
- **GPT-4o Integration:** Utilizes the latest OpenAI model for intelligent text transformation.
- **Confidence Scoring:** Displays estimated accuracy for each transcription.
- **Context Preservation:** Ensures the original intent is maintained while optimizing for AI assistants.

### Other Features
- **Dual Display:** Shows both Tamil transcription and the generated structured prompt.
- **Copy / Download:** Easily share or save generated output.
- **Status Tracking:** Real-time indicators for recording, transcription, and processing.
- **Clear History:** One-click reset to clear all previous results.

---

## Technical Stack

### Frontend
- React 18  
- TypeScript  
- Vite  
- Tailwind CSS  
- shadcn/ui  

### Backend
- Node.js  
- Express  
- OpenAI API Integration  

### Database
- PostgreSQL  
- Drizzle ORM  

### Deployment
- Replit with auto-scaling support
