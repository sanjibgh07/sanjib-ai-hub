# Sanjib AI Hub

A focused directory and control surface for AI models, free API resources, provider routing, and locally installed AI services.

## Scope

- **Models** — discover capable free and low-cost model options.
- **Providers & APIs** — compare API access, context, modality, and practical notes.
- **Local Services** — track installed services such as OmniRoot, OpenCode, and OpenCore.
- **Routing** — architecture for Gemini/Groq/OpenRouter/free providers/local OpenAI-compatible endpoints through a future OmniRoute layer.
- **Safety** — no API keys or secrets are stored in this repository.

## Important

The public website is a static frontend. A browser cannot directly start arbitrary programs on a user's computer. Local-service activation therefore uses a future authenticated local companion/bridge API rather than exposing local processes to the public internet.

## Deployment

The site is designed for GitHub Pages. Pushes to `main` deploy automatically through GitHub Actions once Pages is configured to use **GitHub Actions** as the build/deployment source.

## Architecture

```text
Sanjib AI Hub
├── Models / Providers Registry
├── Free API Discovery
├── OmniRoute (planned routing layer)
├── Local Services
│   ├── OmniRoot
│   ├── OpenCode
│   └── OpenCore
└── Secure Local Bridge (planned)
```

## Security

Never commit API keys, passwords, tokens, cookies, `.env` files, or private connection details. Provider retention/training policies should be checked before sending sensitive information to third-party models.

## License

MIT
