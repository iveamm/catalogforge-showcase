# System overview

CatalogForge has two cooperating codebases behind the public view.

**Catalog data layer (Python)**  
Collects and normalizes metadata, maintains a canonical catalog, tracks source evidence, and prepares reproducible data for downstream processing.

**Resolution and intelligence layer (Node.js / JavaScript)**  
Handles Arabic/Latin identity matching, versioned customer-catalog resolution, ranked candidates, review decisions, and authenticated API workflows. Additional graph and ML models are developed and evaluated separately.

The commercial starting point is **Catalog Match**. Catalog integrity and repair are a related research and product direction, not an assertion of ownership or rights.

This repository intentionally contains only documentation and synthetic examples. It is not the underlying application or a public hosted API. Accuracy claims require independent evaluation on adjudicated examples.

[Architecture](architecture.md) · [API shape](api-examples.md)
