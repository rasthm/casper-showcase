# Casper: a personal AI assistant for Windows

> The source code is private. This page explains what Casper is and what it is built with.

Casper is a voice assistant that lives on my Windows PC and on my phone. Say "Hey Casper" and it listens, thinks with Claude, talks back and gets things done on the computer. It also runs my studio's background jobs: drafting sales replies and making Instagram reels.

## What it does

**Voice and presence**
- A local "Hey Casper" wake word, trained on my own voice. It uses a keyword spotter, then a voice-activity and Whisper check, so it works on the first try without sending audio to the cloud.
- A small Dynamic Island–style pill on the desktop shows when Casper is listening, thinking or speaking. The Copilot key works as an on/off switch.
- Natural spoken replies with ElevenLabs voices, in English, Malayalam and many more languages (Hindi, Tamil, Telugu, Kannada and others). Languages are added from the control panel.
- Conversation mode: patient listening, follow-up questions, and "goodbye" to end.

**Doing things on the PC**
- A Claude brain with full tool access, run through Claude Code, that can work on files, the web and apps.
- Casper can see the screen and the camera (YOLOX object detection running locally on ONNX Runtime).
- It types into any window by voice.
- It plays Spotify by voice, inside Casper itself. The Spotify app never opens, and music gets quieter while Casper is listening.
- Meeting notes: it records both me and the call, writes a live transcript, and has Claude Opus write up the notes.

**From the phone**
- A phone app to chat with Casper from anywhere, with master switches, progress updates on long jobs, and Yes / No prompts before anything that can't be undone.
- Live voice calls to Casper from the phone, through a Cloudflare relay.

**Sentinel and control panel**
- Sentinel, Casper's command centre, with its own memory, plans and a map of everything it knows.
- A control panel for settings, languages, voices, connectors and MCP servers.

**Studio jobs** (for Halo Automations)
- Sales worker: drafts replies to website and Instagram enquiries for my desk to approve, never sends anything on its own, books calls, writes meeting notes and drafts proposals from them.
- Reel engine: plans, voices and renders Instagram reels about the studio's products on a daily schedule, in rotating looks, and uploads them to my desk for approval.

## Built with

| Area | Tools |
|---|---|
| App | Electron (castlabs build with Widevine, for Spotify), Node.js |
| Brain | Claude (Anthropic) through Claude Code, with Opus, Sonnet and Haiku chosen per task |
| Speech in | sherpa-onnx keyword spotting, voice activity detection, Whisper (all local) |
| Speech out | ElevenLabs |
| Vision | YOLOX on ONNX Runtime; screen capture |
| Music | Spotify, played in-app |
| Phone and relay | Cloudflare Workers |
| Reels | HyperFrames (HTML to video), FFmpeg, ElevenLabs |
| Messaging | Gmail, Instagram, WhatsApp, Telegram, Google Calendar |

## Related

- [rasthm-desk-showcase](https://github.com/rasthm/rasthm-desk-showcase): the web desk where I approve what Casper's agents prepare.

---
© 2026 Rasthm.
