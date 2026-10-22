# Architecture

CatalogForge separates data preparation from serving, so catalog matching does not require loading every research model.

```mermaid
flowchart LR
    subgraph Data["Catalog preparation · Python"]
        A["Source metadata"] --> B["Normalization & evidence"]
        B --> C[("Canonical catalog")]
        C -.-> G["Graph / ML research"]
    end
    subgraph Match["Catalog resolution · Node.js"]
        D["Customer reference catalog"] --> E["Versioned index"]
        F["Incoming records"] --> R["Identity + candidate ranking"]
        E --> R
        R --> H{"Decision"}
        H --> I["MATCH"]
        H --> J["REVIEW"]
        H --> K["NO_MATCH"]
    end
    C -.-> E
```

The main flow is reference-catalog matching: resolve Arabic/Latin variants, rank candidates, and return a traceable decision. Research models are separate from the lightweight matching runtime.

[Back to overview](../README.md)
