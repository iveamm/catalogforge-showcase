# API shape

The private API supports customer reference catalogs and batch reconciliation. Routes and payloads below are illustrative; they are not a public endpoint.

Create a reference catalog with `POST /v1/catalogs`. Submit rows with `POST /v1/resolve/jobs` using the appropriate catalog version.

```json
{
  "catalog_id": "demo-catalog",
  "catalog_version_id": "demo-v1",
  "rows": [
    {
      "customer_record_id": "incoming-001",
      "track_title": "Laylet Saif",
      "primary_artist": "Lina Kareem"
    }
  ]
}
```

A resolved row may contain:

```json
{
  "source_customer_id": "incoming-001",
  "selected_target_id": "target-001",
  "decision": "MATCH",
  "reason_codes": ["HIGH_SCORE", "CLEAR_MARGIN"]
}
```

All IDs, names, and decisions here are synthetic. A score is not an independently calibrated probability, and actual outcomes depend on catalog evidence and decision policy.

[Back to overview](../README.md)
