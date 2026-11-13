# Autonomous WhatsApp Appointment Booking Agent

## Overview
This system acts as a 24/7 virtual assistant on WhatsApp for clinics and service businesses. Instead of manual phone calls or delayed messaging, the agent chats naturally with patients, checks real-time availability, and books, reschedules, or cancels appointments automatically while keeping client data secure.

## What Powers It
* **Automation:** n8n (Self-hosted)
* **Intelligence:** Anthropic Claude (Claude Haiku)
* **Memory & State:** PostgreSQL Chat Memory
* **Integrations:** WhatsApp Cloud API, OpenAI Whisper (for voice note transcription), and QClínicas Cloud API

## How It Works

### 1. Ingestion & Voice Transcription
* **Instant Capture:** Receives inbound customer messages via WhatsApp webhooks instantly and securely.
* **Smart Media Handling:** Automatically detects whether the message is text or voice. If a client sends a voice note, it downloads the audio file and transcribes it into clean text using OpenAI Whisper.

### 2. Contextual AI Agent & Memory
* **Real-Time Context:** Injects current date and time references dynamically into the system prompt so the AI always knows what day "tomorrow" or "next Friday" is.
* **Persistent Memory:** Uses PostgreSQL to remember conversation history, allowing for natural, multi-turn dialogue.
* **Strict Guardrails:** Enforces clinic business hours, holiday closures, service pricing, and data privacy rules (never exposing other patients' data).

### 3. Automated Scheduling & Tools
The AI uses secure API tools to interact directly with the scheduling software:
* **📅 Check Availability:** Instantly queries the clinic's calendar to find open slots for specific dates and services.
* **✨ Book Appointments:** Collects required client details (Name, DNI/NIE, Treatment, Date, and Time) and securely registers the appointment.
* **❌ Cancel Bookings:** Handles cancellation requests safely by verifying appointment IDs before executing removal.
* **💬 Automated Reply:** Formats and sends a friendly, concise confirmation or response back to the user on WhatsApp.

## Business Impact
This automation eliminates missed calls and reduces front-desk workload entirely. Patients can book appointments instantly at any hour of the day through WhatsApp, while complex calendar checks and data entry happen seamlessly on autopilot.