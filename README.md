# Jarvis

A personal AI operating system built around a four-layer Claude architecture. 
Jarvis monitors inputs from the world, decides what is significant, scores 
whether to interrupt, generates context-aware responses, and acts — or asks 
first when uncertain.

## Architecture

- **Input Layer** — WHOOP sleep data, calendar, email, voice, screen reader, 
  markets, weather, news
- **Context Engine** — three-tier memory: long-term DB (identity, goals, 
  preferences), session RAM (today only), event bus (detected but undelivered 
  signals)
- **Event Generator** — Claude call #1, significance detector, decides what 
  matters without hardcoded rules
- **Relevance Loop** — Claude call #2, scores interrupt-worthiness against 
  current activity, 20-minute cooldown gate
- **Meta-Prompt Layer** — Claude call #3, writes and executes the optimal 
  response for the moment
- **Ambiguity Checker** — Claude call #4, determines whether to act immediately 
  or surface a confirmation. Communications block (send_email, send_message, 
  post_social) is hardcoded off at code level — Claude cannot override it.

## Stack

Node.js · Claude API · Supabase · BullMQ · ElevenLabs · Whisper · Electron · 
Swift daemon (screenshot capture) · AppleScript

## Status

Architecture complete. MVP build begins June 2026.

## Why

I want to understand how autonomous AI systems actually work at an architectural 
level — not as a user but as a builder. Jarvis is the project that forces that.
