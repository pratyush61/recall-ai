# Recall AI: AI-Powered Study Set Generator

Turn any topic or a pile of notes into a ready-to-use study set in seconds. Recall uses the Gemini API to generate structured **flashcards** and a **quiz**, so you spend your time learning instead of making study material.

Unlike a chatbot, Recall returns structured study content that is validated before it is shown, so the app never renders broken or unexpected output.

**[Live Demo](https://recall-ai.vercel.app)** | **[Screen Recording](https://drive.google.com/file/d/1dcKVwqh_c3CGSxGfU5rnZiYL00Ud34Dp/view?usp=sharing)**

---

## Features

**Study tools**
- Generate a study set from a topic or pasted notes
- Review material with interactive flashcards
- Practise with a quiz and revisit the questions you got wrong
- Shuffle the study set
- Export your study material as Markdown
- Keyboard shortcuts for quiz interactions

**Reliability**
- Validates model output before rendering it
- Handles malformed responses, empty responses, API failures and slow requests
- Cancel a generation that is in progress
- Prevents stale responses from overwriting newer state
- Retry after an error
- Loading, empty and error states throughout the interface
- Error boundary as a fallback for unexpected rendering errors
- Best-effort request rate limiting

**Experience**
- Draft is saved locally, so you can pick up where you left off
- Responsive layout for desktop and smaller screens

---

## Tech Stack

| Area | Technology |
| --- | --- |
| UI | React |
| Build tool | Vite |
| Language | JavaScript |
| AI | Gemini API |
| Backend | Server-side API handler (keeps the API key private) |
| Deployment | Vercel |

---

## How It Works

1. You enter a topic or paste your notes.
2. The app sends the request to a server-side API handler.
3. The handler calls Gemini to generate structured study content.
4. The response is parsed and validated.
5. Valid content is shown as flashcards and quiz questions.
6. You can review, practise, retry, shuffle, export or clear the study set.

---

## Getting Started

### Prerequisites

- Node.js and npm
- A Gemini API key

### Installation

```bash
git clone https://github.com/pratyush61/recall-ai.git
cd recall-ai
npm install
```

### Configure your API key

Copy the example environment file and add your Gemini API key:

```bash
cp .env.example .env
```

Then open `.env` and fill in the key using the variable name shown in `.env.example`.

> **Security:** Never commit API keys to GitHub. `.env` is listed in `.gitignore`, and the key is only used on the server side.

### Run the app

```bash
npm run dev
```

Open the local URL shown in your terminal.

### Build for production

```bash
npm run build
```

---

## Project Structure

```
recall-ai/
├── api/          # Serverless API handler (calls Gemini)
├── server/       # Server-side code
├── src/          # React application
├── docs/         # Documentation
├── index.html
└── vite.config.js
```

---

## Known Limitations

- AI-generated content can be incorrect or incomplete. Verify important information against trusted sources.
- Streaming generation is not implemented yet.
- Follow-up refinement of an existing study set is not implemented yet.
- History is limited, so this is not a full multi-session study manager.
- Rate limiting is best-effort and in-memory. In serverless deployments, limits may not be shared across instances.
- Very long notes may be rejected by the input-length limit.
- Output quality and availability depend on the Gemini API.

---

## Roadmap

- [ ] Streaming generation
- [ ] Refine an existing study set with follow-up prompts
- [ ] Save and manage multiple study sets
- [ ] Spaced-repetition scheduling

---

## Author

Built by [pratyush61](https://github.com/pratyush61).

If you find this project useful, consider giving it a star.
