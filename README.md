# Presence Resonance

A genealogy and family-history platform that reconstructs family trees from source records (GEDCOM and beyond), maps them across time and geography, and surfaces the connections and patterns — the "resonance" — that run through a family's history.

## Project structure

```
presence-resonance/
│
├── apps/
│   ├── web/                 Frontend application
│   └── api/                 Backend API service
│
├── packages/
│   ├── core/                Shared types, utilities, and constants
│   ├── auth/                Authentication and authorization
│   ├── genealogy/           Core genealogy domain models (people, relationships, events)
│   ├── gedcom/               GEDCOM parsing, import, and export
│   ├── family-graph/        Family tree graph construction and traversal
│   ├── geography/           Place resolution, geocoding, migration paths
│   ├── timeline/            Chronological event timelines
│   ├── media/                Photo and document asset management
│   ├── resonance/           Cross-generational pattern and connection analysis
│   ├── ai-interpreter/      AI-assisted interpretation of records and documents
│   └── visualization/       Family tree, timeline, and map rendering
│
├── data/
│   ├── schemas/              Data validation and JSON schema definitions
│   ├── gedcom/                Sample and test GEDCOM files
│   ├── genealogy/            Seed and reference genealogy datasets
│   └── research/              Research notes and source citations
│
├── infrastructure/
│   ├── database/             Schema, migrations, and database config
│   ├── authentication/       Auth provider configuration
│   ├── storage/               Object storage configuration
│   └── deployment/           CI/CD and deployment manifests
│
├── docs/
│   ├── architecture/         System architecture documentation
│   ├── research/              Research methodology
│   ├── security/               Security policies and threat model
│   └── api/                    API reference
│
└── README.md
```

## Getting started

This is a pnpm workspace.

```bash
pnpm install
pnpm build
pnpm dev
```

Requires Node.js >= 20 and pnpm >= 9.
