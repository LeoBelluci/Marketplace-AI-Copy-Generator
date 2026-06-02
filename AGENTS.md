# AGENTS.md

## Project Name

Marketplace AI Copy Generator

## Main Goal

Build a full-stack application that generates optimized marketplace ad copy using AI.

The system must generate:

- Optimized titles
- Product descriptions
- Short descriptions
- Bullet points
- Keywords
- SEO score
- Conversion score
- Warnings
- Alternative title variations
- Generation history

The user must be able to copy the generated title, description, bullets and keywords manually.

## Important Scope Rule

Do not build browser automation.
Do not use Chrome automation.
Do not use Playwright.
Do not publish directly to marketplaces.
Do not integrate marketplace accounts in this first version.

The system is only a copy generator and assistant.

## Tech Stack

Frontend:

- React
- TypeScript
- Vite
- TailwindCSS
- React Query
- Zustand
- Axios
- React Router DOM

Backend:

- Python 3.12+
- FastAPI
- Pydantic
- SQLAlchemy
- PostgreSQL
- Alembic
- Gemini API through google-genai
- Pytest

Infrastructure:

- Docker Compose
- PostgreSQL
- Optional Redis only if necessary

## Architecture

Use clean architecture on the backend:

- domain: pure business rules
- application: use cases and ports
- infrastructure: database, repositories, AI gateway
- interfaces: HTTP routes
- ml: scoring and future ML logic

The frontend should be feature-based:

- products
- generator
- history
- settings

## AI Requirements

Use the Gemini API to generate structured ad copy.

The AI response must be validated with Pydantic.

Use JSON output with this structure:

{
  "title": "string",
  "alternative_titles": ["string"],
  "description": "string",
  "short_description": "string",
  "bullets": ["string"],
  "keywords": ["string"],
  "seo_score": 0,
  "conversion_score": 0,
  "warnings": ["string"]
}

## Marketplaces

Support copy generation styles for:

- Shopee
- Mercado Livre
- Amazon
- TikTok Shop
- Generic marketplace

Each marketplace should have its own prompt template.

## UX Requirements

The frontend must have:

- Product input form
- Marketplace selector
- AI generation button
- Loading state
- Generated result card
- Copy title button
- Copy description button
- Copy keywords button
- SEO score card
- Alternative titles section
- Generation history page
- Settings page for prompt templates

## Quality Requirements

- Create complete README files
- Create .env.example
- Add basic unit tests
- Add error handling
- Use type safety
- Use clean folder organization
- Keep secrets out of the repository
- Make the project runnable locally

## Final Deliverable

The project must run with:

Backend:

uvicorn app.main:app --reload

Frontend:

pnpm dev

Docker:

docker compose up -d

## Do not stop after scaffolding

Implement the actual MVP functionality end to end.