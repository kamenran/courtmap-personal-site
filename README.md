# CourtMap + TrialSim

**Live site:** [kamran.codes](https://kamran.codes)

CourtMap + TrialSim is a personal website and legal technology project built by Kamran Eisenberg. The site presents two interactive tools focused on legal reasoning, constitutional doctrine, and educational legal simulation.

The project is intentionally scoped as a polished web application rather than a comprehensive legal research platform. It uses curated data and transparent modeling to make legal concepts easier to explore without claiming to provide legal advice or predict real case outcomes.

## Project Goals

- Present a professional technical profile centered on the intersection of computer science and law
- Build interactive tools for exploring legal systems, not static summaries
- Use software design, graph visualization, and structured data to make legal reasoning more accessible
- Keep the product honest about scope, data limits, and future expansion

## CourtMap

CourtMap is an interactive Supreme Court precedent explorer. It treats cases as connected legal objects, showing how landmark decisions relate through citations, doctrines, constitutional anchors, voting alignments, and overruling relationships.

Current features:

- Curated SCOTUS case dataset
- Searchable case list
- Case detail view with citation, year, court, doctrine, constitutional anchor, holding, and source link
- Plain-English case explanations
- Case brief section
- Doctrine timeline for selected cases
- Before/after doctrine shift view
- D3 precedent graph
- Doctrine path finder
- Justice voting alignment view

Current scope: CourtMap focuses on landmark Supreme Court cases. It is not yet a full Supreme Court database or a substitute for legal research tools.

## TrialSim

TrialSim is an educational legal scenario simulator. It models how simplified legal variables can affect case pressure in hypothetical scenarios.

Current features:

- Scenario presets for criminal procedure, civil liability, AI vendor liability, hiring bias, and fair use disputes
- Adjustable factors for evidence strength, witness reliability, jurisdiction, litigation strategy, and constitutional issues
- Weighted scoring model for case viability, settlement pressure, and dispute risk
- Scenario comparison view
- Argument panels identifying strengths, weaknesses, and likely points of disagreement
- Clear disclaimer that TrialSim is educational and does not predict actual legal outcomes

Current scope: TrialSim is a structured educational model. It is not legal advice and should not be read as a litigation prediction system.

## Technical Stack

- React
- JavaScript
- CSS
- D3.js
- Local structured data
- GitHub Pages
- Custom domain routing through `kamran.codes`

## Data And Architecture

The current version uses curated local data so the interface and product concept are stable. The longer-term architecture is designed for larger legal datasets.

Planned data sources:

- **CourtListener** for Supreme Court opinions, case names, opinion text, citations, and citation graph relationships
- **Supreme Court Database** for issue area, decision direction, justice votes, majority/minority metadata, term/year, and legal issue coding
- **Caselaw Access Project** as a fallback for historical full text and missing metadata

Planned storage direction:

- Neo4j for citation and doctrine graph relationships
- PostgreSQL for structured legal metadata

Schema:

```text
database/courtmap_schema.sql
```

Architecture notes:

```text
docs/courtmap_data_architecture.md
```

## Local Development

Run a local static server:

```bash
python3 -m http.server 4173
```

Open:

```text
http://127.0.0.1:4173/
```

## Deployment

The live site is served from the `gh-pages` branch. The `web/` directory is published to GitHub Pages and connected to:

```text
https://kamran.codes
```

## Roadmap

- Expand the curated SCOTUS dataset
- Import citation relationships from CourtListener
- Add richer justice vote and opinion-author metadata
- Add doctrine-specific views for privacy, equal protection, criminal procedure, and judicial review
- Add more TrialSim scenarios
- Improve model explanations for TrialSim variables
- Improve accessibility and mobile polish
- Add backend/database support if the dataset grows
