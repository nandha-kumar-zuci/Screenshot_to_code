# screenshot-to-code

A simple tool to convert screenshots, mockups and Figma designs into clean, functional code using AI.

Supported stacks:

- HTML + Tailwind
- HTML + CSS
- React + Tailwind
- Vue + Tailwind
- Bootstrap
- Ionic + Tailwind
- SVG
- REACT Type Script

Supported AI models:

- Claude Sonnet 3.5 - Best model!
- GPT-4O-Azure- also recommended!



Keys needed:
- OpenAPI Key
- Anthropic key (optional) - only if you want to use Claude Sonnet, or for experimental video support.


```

## Docker

If you have Docker installed on your system, in the root directory, run:

```bash
echo "OPENAI_API_KEY=sk-your-key" > .env
docker-compose up -d --build
```
Run the backend (I use Poetry for package management - `pip install poetry` if you don't have it):

```bash
cd backend
echo "OPENAI_API_KEY=sk-your-key" > .env
poetry install
poetry shell
poetry run uvicorn main:app --reload --port 7001
```

If you want to use Anthropic, add `ANTHROPIC_API_KEY` to `backend/.env`. You can also set up the keys using the settings dialog on the front-end (click the gear icon after loading the frontend).

Run the frontend:

```bash
cd frontend
yarn
yarn dev
```

Open http://localhost:5173 to use the app.

If you prefer to run the backend on a different port, update VITE_WS_BACKEND_URL in `frontend/.env.local`

For debugging purposes, if you don't want to waste GPT4-Vision credits, you can run the backend in mock mode (which streams a pre-recorded response):

```bash
MOCK=true poetry run uvicorn main:app --reload --port 7001
The app will be up and running at http://localhost:5173. Note that you can't develop the application with this setup as the file changes won't trigger a rebuild.

