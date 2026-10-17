# API Example

Create a catalog:

`POST /v1/catalogs`

Submit a resolution job:

`POST /v1/resolve/jobs`

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

Example result:

```json
{
  "source_customer_id": "incoming-001",
  "selected_target_id": "target-001",
  "decision": "MATCH",
  "confidence": 0.97,
  "calibrated_probability": false,
  "reason_codes": ["HIGH_SCORE", "CLEAR_MARGIN"]
}
```

All records shown here are synthetic.
