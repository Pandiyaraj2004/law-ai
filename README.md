# Law AI

> A Flask prototype that turns a country and a written scenario into an AI-generated legal-information response.

**Python · Flask · Gemini API · JavaScript · HTML · CSS**

## Workflow

1. Enter a country and describe a scenario.
2. The browser sends JSON to `POST /generate`.
3. Flask validates the required fields and sends a structured prompt to Gemini.
4. The response is returned to the interface and can be downloaded as text.

## API surface

| Route | Purpose |
| --- | --- |
| `GET /` | Render the interface |
| `POST /generate` | Accept `country` and `situation`; return generated text |
| `POST /download` | Accept `response`; return a text file |

## Local setup

```bash
git clone https://github.com/Pandiyaraj2004/law-ai.git
cd law-ai
python -m pip install flask flask-cors google-generativeai
```

Before starting, replace the hardcoded API credential in `app.py` with server-side environment configuration. The code targets a legacy Gemini model and client; confirm availability with your provider and update the integration as needed.

```bash
python app.py
```

Open http://localhost:5000.

## Explore the implementation

- [app.py](app.py): validation, prompt construction, provider call, download route.
- [templates/index.html](templates/index.html): user interface.
- [static](static): browser behavior and styling.

## Scope and limitations

An integration prototype for generated legal information. It does not retrieve or verify authoritative legal sources and is not a substitute for qualified legal advice. Use fictional scenarios when demonstrating it: the current implementation logs the submitted scenario and uses a shared download filename. Production use requires privacy controls, per-request downloads, credential management, and deployment hardening.

---

Built by **Pandiyaraj A** · [Portfolio](https://pandiyaraj.netlify.app/) · [GitHub](https://github.com/Pandiyaraj2004) · [LinkedIn](https://www.linkedin.com/in/pandiyaraj-a-mca/)
