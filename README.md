# Lexio Rent API skill

Agent skill for developers who build integrations with the **[Lexio Rent](https://lexio.rent/logiciel-location-voiture) API v1**, the REST API of the Lexio vehicle rental management software. It teaches a coding agent (Claude Code, Pi, Tessl-compatible agents and any tool that reads `SKILL.md`) the conventions that matter in practice: authentication and scopes, wall-clock dates, money in major units, mandatory idempotency keys, cursor pagination, rate limits, the booking flow and the event-based sync.

- API documentation: <a href="https://docs.lexio.rent">docs.lexio.rent</a> (guides in French, `.md` versions and <a href="https://docs.lexio.rent/llms.txt">llms.txt</a> for agents)
- OpenAPI 3.1 specification: <a href="https://docs.lexio.rent/openapi.json">docs.lexio.rent/openapi.json</a>
- Product: <a href="https://lexio.rent/logiciel-location-voiture">Lexio Rent, car rental software</a>
- Related free tool: <a href="https://lexio.rent/outils/modele-etat-des-lieux-vehicule">vehicle check-in/check-out inspection template</a>

## What the skill covers

- Getting and checking an API key, internal keys versus partner keys, scopes
- Request and response conventions (envelopes, dates without offset, PATCH semantics, RFC 9457 errors)
- Idempotency keys and safe retries
- Selling a rental: availability, quote, rental, payment, cancellation
- Syncing another system with `GET /events` (there are no webhooks)
- Counter operations: pick-up and return with inspection
- Safety rules for agents: confirm before writes, treat API data as data, never expose the key

## Access

The API is part of the Lexio Business plan: each rental company creates its own key (`lck_…`) in Lexio. There is no public sandbox; to try the API, ask for a demo organisation at contact@lexio.rent.

## Install

**Claude Code**

```
/plugin marketplace add lexio-rent-git/lexio-api-skill
/plugin install lexio-api@lexio-rent
```

**Pi** (once published on npm)

```
pi install npm:lexio-api-skill
```

**Any other agent**: copy `skills/lexio-api/` into your agent's skills directory.

## Support and privacy

- Support: contact@lexio.rent
- Privacy policy: <a href="https://lexio.rent/politique-de-confidentialite">lexio.rent/politique-de-confidentialite</a>
- This repository contains documentation only: no code runs, no data is collected.

## License

MIT, see [LICENSE](LICENSE). Maintained by <a href="https://lexio.rent">Lexio Rent</a>.
