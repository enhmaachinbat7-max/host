# TumruuGPT — Local proxy for ChatGPT API

This small project adds a local Node.js proxy that forwards chat requests to the OpenAI Chat API so your client code doesn't expose the secret API key.

Setup (Windows PowerShell):

```powershell
# Install dependencies
npm install

# Set your OpenAI API key in the environment (PowerShell)
$env:OPENAI_API_KEY = 'sk-...'

# Start the server
npm start

# Open the demo in your browser
Start-Process "http://localhost:3000/index.HTML"
```

Notes:
- Keep your `OPENAI_API_KEY` secret. Do not commit it to source control.
- The server serves the repository root as static files; it exposes `POST /api/chat` which expects JSON `{ "message": "..." }` and returns `{ "reply": "..." }`.
- You can override the OpenAI model with `OPENAI_MODEL` environment variable. Default: `gpt-4o-mini`.

If you want a Python/Flask implementation instead, tell me and I'll add it.
